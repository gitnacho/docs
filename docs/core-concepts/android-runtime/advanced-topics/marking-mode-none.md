---
title: "Optimizing Performance Using markingMode: none"
description: "How to enable markingMode:none in your NativeScript mobile app and prevent potential problems"
position: 3
slug: marking-mode-none
---

# Optimizing Performance Using markingMode: none

Starting with NativeScript 3.2, a new (experimental at the time) feature was added to the Android runtime called `markingMode`. Its purpose is to speed up garbage collection in the V8 engine. In some cases, a GC pass could take from 0.5 to 1 second and since it runs on the main UI thread, the user would experience a frozen app until GC is done. Setting “markingMode” to “none” will speed up the garbage collection greatly, so it would be less noticeable (if at all) to the app user. The downside of this approach is that some objects could be collected while their counterparts (in V8 or Android) are still in use. Such case is when JavaScript objects are referenced only from native code and in the eyes of the V8 GC no JS object holds reference to them. In other words – the objects are no longer “marked” as used and the V8 GC might collect them too early.

The code inside `tns-core-modules` and all plugins published by the NativeScript Team (since version 5.1.0) are written in such a way, that it does not depend on the scope to keep those Java/Kotlin instances alive. This makes apps using these plugins fully compatible with the much more performant `markingMode: "none"` option.

## Benefits and drawbacks of using markingMode: none

The biggest benefit of setting `markingMode` to `none` is a more responsive app – an app that does not slow down if you use it for an extended amount of time.

The main drawbacks are:

* It is up to the plugin developer to manage the plugin-related memory correctly. There might be plugins that do not support the feature and could crash the app with a "cleared reference" exception.
* It is up to the app developer to manage the app memory correctly. The app code itself might also need to be updated in order to keep JS object references and prevent unwanted collection.

## Updating an app or a plugin to support `markingMode: none`

First, to instruct any app to use this feature we need to add the following in the [Android-specific custom flags(app/package.json)](./custom-flags):

``` JSON
"android": {
  "markingMode": "none",
}
```

If the app behaves correctly after this change - great. Sometimes, however, some sporadic errors/crashes occur, especially related to memory management, like any of the following:

* `Error: com.tns.NativeScriptException: Attempt to use cleared object reference id=<some-object-id-number>`
* `The JavaScript instance no longer has available Java/Kotlin instance counterpart`

In such cases additional work has to be done. Have in mind the problem could be either in the app code, or in some plugin(s) used by the app. In both cases the resolution is identical.

### Let’s start with an example

``` JavaScript
var implementor = new android.native.Implementor();     // native class
var callback = new android.native.NCallback({           // native interface
    getMessage: function () {
        implementor.getMessage();
    }
});
android.native.Executor.printWithDelay(callback, 3s);
```

The implementor is enclosed by the callback implementation, but with `markingMode: none` enabled the framework no longer takes care of finding out that connection. So, when GC happens in V8 or in Android the `implementor` instance (or its native representation) is GC'ed. This can result in either Java/Kotlin or JavaScript instance missing and upon calling of the `callback` an "Attempt to use cleared object reference" or "JavaScript instance no longer has available Java/Kotlin counterpart" error is very likely to occur.

### Solution

To fix the previous example you must keep implementor from being GC'ed, by attaching it to the global object (or some other long-lasting object, exported module or wherever you see fit) which will ensure it will not be GC'ed prematurely. Below, the `implementor` is attached to `global` for the sake of the example:

``` JavaScript
var implementor = new native.Implementor();
global.implementor = implementor;
var callback = new native.NCallback({
    getMessage: function () {
        global.implementor.getMessage();
    }
})
native.Executor.printWithDelay(callback, 3s);
```

Naturally, you must manage the lifecycle of the implementor and release it when it is no longer needed:

``` JavaScript
global.implementor = null;
```

> **Note**: To see a more concrete example of the above scenario using `markingMode: none`, run [this example](https://github.com/NativeScript/marking-mode-example)

## Testing an app for `markingMode: none` related issues

`markingMode: none` applies to Android only, so testing for issues implies testing your app in Android Emulator or real Android device. Because bugs of this kind occur pretty randomly, there is not a single and universal way to find them. Below are some general tips on how to test/maintain an app:

* Look for code fragments where native Java/Kotlin instances are created and ones in which these instances are used from inside event handlers, callbacks, functions of extended classes. Have in mind that in such cases if the JS instance reference becomes weak (i.e. garbage collectable), this can be a source of a problem. In such case make sure you make it strong, i.e. not collectable. Also make sure to dispose it when no longer needed.
Below are 2 possible solutions for some common cases:
  + {N} View classes - any native views or listeners should be kept in private properties on your View class so the lifetime of its native objects will be tied to the JavaScript View instance.
  + Listeners - like the example above - store any native instances in the global scope if you need it to be accessed from callbacks, closures, etc.
* [Monkey testing](https://developer.android.com/studio/test/monkey) - this is a CLI-based way of testing your apps by generating random events like clicks, gestures, etc. It is best to pin your app before starting the monkey test. Thus "the monkey" will interact only with the app and not with the whole OS.
Example command to start testing:

  ``` Shell
  adb shell monkey --throttle 200 40000
  ```

  To stop the monkey:

  ``` Shell
  adb shell ps | awk '/com\.android\.commands\.monkey/ { system("adb shell kill " $2) }'
  ```

  In order to unpin a pinned app:

  ``` Shell
  adb shell am task lock stop
  ```

## Summary

Every native object instantiated in JS/TS, like:

``` JavaScript
var implementor = new android.native.Implementor();
```

... and which is also enclosed by a function of an extended class, event handler, etc:

``` JavaScript
...
getMessage: function() {
    implementor.getMessage();
}
...
```

... needs to be managed by the developer. You should decide when it is not needed any more and can be let go for GC.
