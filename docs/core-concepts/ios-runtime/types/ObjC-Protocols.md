---
nav-title: "Objective-C Protocols"
title: "Objective-C Protocols"
description: "Describes how Objective-C protocols are exposed."
position: 2
---

# Objective-C Protocols

Objective-C protocols describe an API Objective-C classes may implement. JavaScript does not have a matching counterpart. For every Objective-C Protocol we expose a JavaScript object that identifies the protocol.

For example given the following Objective-C declarations:

``` Objective-C
@protocol MyProtocol
* (void)helloWorld;
@end

@interface MyClass : NSObject <MyProtocol>
@end
```

Will be exposed as:

``` JavaScript
console.log(MyClass.conformsToProtocol(MyProtocol)); // true

var instance = MyClass.alloc().init();
console.log(instance.conformsToProtocol(MyProtocol)); // true
```

You can get the name of a protocol as a string and back:

``` JavaScript
var protocol = NSProtocolFromString("MyProtocol");
console.log(NSStringFromProtocol(protocol)); // "MyProtocol"
console.log(protocol === MyProtocol); // true
```

Like [Objective-C classes](ObjC-Classes.md), Objective-C protocols too have a prototype and constructor methods. For example:

``` Objective-C
@protocol TNSProtocol
@property int aProperty;
+ (void)staticMethod;
* (void)instanceMethod;
@end
```

``` JavaScript
var staticMethod = TNSProtocol.staticMethod;
var instanceMethod = TNSProtocol.prototype.instanceMethod;
var aProperty = Object.getOwnPropertyDescriptor(TNSProtocol.prototype, 'aProperty');
```

Although these methods cannot be called directly, it can be useful in some rare cases to get the method from the protocol and [`call`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)/[`apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) it to an Objective-C object instance that privately conforms to the given protocol.

These protocol wrapper objects can also be used in the [extension API](../how-to/ObjC-Subclassing.md) to create derived Objective-C classes that implement the protocols.

> **Note**: In case of conflicts with other types, the name has the `Protocol` suffix.

``` JavaScript
var klass = NSObject;
var protocol = NSObjectProtocol;
```
