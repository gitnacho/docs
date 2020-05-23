---
title: "Custom Flags"
description: "Configure various V8 engine flags in order to improve the performance of your app, or to obtain more comprehensive information during debugging"
position: 4
previous_url: /core-concepts/android-runtime/advanced-topics/v8-flags
slug: android-custom-flags
---

# Custom Flags

The V8 engine comes with a set of controlling flags that may be useful for fine-grained tuning. You can set these flags in the [secondary package.json configuration file]({% slug structure %}#apppackagejson). This article contains some of the available flags and short explanation on how you can use them. For a complete list of all V8 flags, see the [Flag Definitions header file](https://github.com/v8/v8/blob/6.9.247/src/flag-definitions.h) in GitHub.

## Expose Garbage Collector

The `--expose_gc` flag exposes a global `gc()` function which can be helpful in [advanced memory management scenarios]({% slug android-memory-management %}).

``` JSON
{
    ...
    "android": {
        "v8Flags": "--expose_gc"
    }
    ...
}
```

## Marking Mode

The `markingMode: none` flag instructs NativeScript apps to use a different mode for garbage collection, providing significant performance boost. To enable it:

``` JSON
{
    ...
    "android": {
        "markingMode": "none"
    }
    ...
}
```

> **Note**: Use `markingMode: none` with caution. Unexpected errors related to premature objects collection may occur. [More information on proper memory management using `markingMode:none`](./marking-mode-none).

## Timezone Changes

For improved performance, V8 keeps a cache of various values used for date and time computation. This may lead to a negative side effect for the application because changes made to the current timezone will not be reflected until the application is restarted. While this is not a common requirement for most applications, there are some circumstances where this behavior might be needed. To enable this scenario, you can set the `handleTimeZoneChanges` flag:

``` JSON
{
    ...
    "android": {
        "handleTimeZoneChanges": true
    }
    ...
}
```

As a result, the application will register a [BroadcastReceiver](https://developer.android.com/guide/components/broadcasts) which will be responsible for the [ACTION_TIMEZONE_CHANGED](https://developer.android.com/reference/android/content/Intent.html#ACTION_TIMEZONE_CHANGED) event and automatically invalidate the corresponding cache. Subsequent calls to `new Date()` will then take into account the new timezone.

## Maximum Log Message Size

By default, all messages sent to Logcat are limited to 1024 characters and larger messages are automatically truncated. This value can be controlled with the `maxLogcatObjectSize` field:

``` JSON
{
    ...
    "android": {
        "maxLogcatObjectSize": 2048
    }
    ...
}
```

## Force Log

When you are using a release build there will be no logs to the console, so if you still want to have your console logs you need to enable the `forceLog` flag:

``` JSON
{
    ...
    "android": {
        "forceLog": true
    }
    ...
}
```

## Use V8 Symbols

If you want to use V8 API in your application code or you want to have the V8 symbols included in the `libNativeScript.so` file inside the application when built in **release** mode, you will need to enable the `useB8Symbols` flag:

``` JSON
{
    ...
    "android": {
        "useV8Symbols": true
    }
    ...
}
```

## Configuring automatic garbage collection

There are three parameters used for configuring the frequency and conditions of automatic triggerring of garbage collections in the JavaScript world. These are `gcThrottleTime`, `memoryCheckInterval` and `freeMemoryRatio`. For detailed explanation of their behavior please refer to the `Syncronizing Garabage Collectors` section in [Memory Management]({% slug android-memory-management %}#syncronizing-garabage-collectors)
