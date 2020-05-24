---
title: Project Structure
description: Learn the basic project structure of а NativeScript application - app, app resources, platforms
position: 120
slug: structure
previous_url: /structure
---

# Project Structure

{% nativescript %}

The default structure of a blank NativeScript project consists of a root folder that contains the `app`, `platforms` and `node_modules` directories, and a `package.json` configuration file.

``` Shell
myApplication/
└── app
    ├── App_Resources
    └── ...
├── node_modules
├── platforms
└── package.json
```

{% endnativescript %}{% angular %}

The default structure of a blank NativeScript + Angular project consists of a root folder that contains the `src`, `platforms`, `node_modules` and `hooks` directories, and several configuration files amongst which the most important is the `package.json`.

``` Shell
myApplication/
├── App_Resources
└── src
    ├── app
    └── ...
├── hooks
├── node_modules
├── platforms
├── package.json
├── tsconfig.json
└── ...
```

{% endangular %}

There are several other directories and configuration files that can be present in your project based on the initial template, the programming language (JavaScript or TypeScript) or the plugins that you are using in your application. This article covers the files and folders that are always present in a NativeScript project, as well as some of the more common ones that you may encounter while developing your app.

## The {% nativescript %}app/{% endnativescript %}{% angular %}src/{% endangular %} directory

The {% nativescript %}`app`{% endnativescript %}{% angular %}`src`{% endangular %} directory in the root of the project is the development space for your project. **Place all your common and platform-specific code in this directory.** When the app is prepared for a build, the NativeScript tooling copies relevant content to the platform-specific folders for each target platform.

In the {% nativescript %}`app`{% endnativescript %}{% angular %}`src`{% endangular %} directory, you can use **platform-specific files** to provide customized functionality and design for each target platform. To indicate that a file is platform-specific, make sure that the file name is in the following format: `name.ios.extension` or `name.android.extension`. For example: `main.ios.js` or `main.android.js`.

You can develop shared functionality or design in common files. To indicate that a file is common, make sure that the file name does not contain a `.android.` or `.ios.` string.

{% nativescript %}

In the `app` folder, you will also find the `App_Resources` directory.

{% endnativescript %}

> **Note**: The location of the `{% nativescript %}app{% endnativescript %}{% angular %}src{% endangular %}` directory can be overridden in the [nsconfig.json file](#the-nsconfigjson-file).

### {% nativescript %}app{% endnativescript %}{% angular %}src{% endangular %}/package.json

This is a secondary `package.json` file in which you can specify the entry point file of the app and to configure the behavior of the NativeScript runtimes. Below is an example of a basic secondary `package.json` file.

{% nativescript %}

``` JSON
{
    "main": "app.js",
    "discardUncaughtJsExceptions": true,
    "android": {
        "v8Flags": "--expose_gc",
        "forceLog": true
    },
    "ios": {
        "jscFlags": "--dumpOptions=2 --validateOptions=1"
    }
}
```

{% endnativescript %}{% angular %}

``` JSON
{
    "main": "main.js",
    "discardUncaughtJsExceptions": true,
    "android": {
        "v8Flags": "--expose_gc",
        "forceLog": true
    },
    "ios": {
        "jscFlags": "--dumpOptions=2 --validateOptions=1"
    }
}
```

{% endangular %}

#### Discarding JavaScript Exceptions Called from Native

Normally, an unhandled exception from JavaScript code called from a native API will crash the application showing the stack trace. If you want to prevent such crashes you can override this behavior using the `discardUncaughtJsExceptions` flag.

All discarded exceptions can be processed in the app by either subscribing to the [application.discardedErrorEvent](/api-reference/modules/_application_#discardederrorevent) and using the received [DiscardedErrorEventData instance](/api-reference/interfaces/_application_.discardederroreventdata), or by assigning a one-argument function to `global.__onDiscardedError` which will receive the exception as a [NativeScriptError instance](/api-reference/interfaces/_nativescript_error_d_.nativescripterror). Usually you would want to log and/or report the exception to analytics.

For example:

``` JavaScript
var application = require("application");

application.on(application.discardedErrorEvent, function (args) {
    const error = args.error;

    console.log("Received discarded exception: ");
    console.log(error.message);
    console.log(error.stackTrace);
    console.log(error.nativeException);
    //report the exception in your analytics solution here
});
```

#### Android Runtime Configuration

For description of the flags which are specific to the Android runtime see the [Android custom flags article]({% slug android-custom-flags %}).

#### iOS Runtime Configuration

For description of the flags which are specific to the iOS runtime see the [iOS custom flags article]({% slug ios-custom-flags %}).

##{% nativescript %}# app/{% endnativescript %}App_Resources

The `App_Resources` folder contains the platform-specific resources of the application (icons, configuration files etc.):

* The configuration files that are respected by the NativeScript tooling are the `App_Resources/Android/src/main/AndroidManifest.xml` for Android, and the `App_Resources/iOS/Info.plist` for iOS.

* The `App_Resources/iOS/build.xcconfig` or `App_Resources/Android/app.gradle` files can be used to add or remove additional build properties for the iOS and Android platforms, respectively.

* Native Android source code can be dropped in at `App_Resources/Android/src/main/java` (after creating the proper package subdirectory structure), while native iOS source code – at `App_Resources/iOS/src/` (more info can be found [here]({% slug ios-source %}))

* Metadata filtering rules can be specified in `App_Resources/Android/native-api-usage.json` and `App_Resources/iOS/native-api-usage.json` respectively. For more detailed description of this feature read [this article]({% slug metadata %})

## The **platforms** Directory

The `platforms` directory is created when you start a build or add a target platform to your project. The NativeScript tooling creates a new subdirectory with the respective platform name. These subdirectories have the platform-specific project structure required for native development with the native SDKs of the platform. When the project is prepared for build, the NativeScript tooling copies relevant content from the {% nativescript %}`app`{% endnativescript %}{% angular %}`src`{% endangular %} directory to the platform-specific subdirectory for each target platform.

> **Important**: Avoid editing files located in the `platforms` subdirectories because the NativeScript CLI overrides them with the content of the {% nativescript %}`app`{% endnativescript %}{% angular %}`src`{% endangular %} directory during the `prepare <Platform>` process.

## The **package.json** File

The main `package.json`, which is located in the root directory of the project, contains details about the application, its dependencies and other helpful information. You can set [common npm package.json properties](https://docs.npmjs.com/files/package.json) like `author`, `description` and `version`, or specify the npm packages and [NativeScript plugins]({% slug plugins-infrastructure %}) on which your app depends by modifying the `dependencies` and `devDependencies` attributes.

The root `package.json` also contains several NativeScript-specific properties which are placed inside the `nativescript` object:

* **id** - Specifies the unique application identifier (App ID) of the app. To be able to build for both Android and iOS, your App ID must be unique and contain two or more strings, separated by a dot. Each string must start with a letter and should contain only letters and numbers. The app identifier must not start with an uppercase letter. For more information about the App ID and how to specify different identifiers for iOS and Android, see [What is App identifier]({% slug changing-appid %}).
* **tns-android.version** - Specifies the version of the Android runtime. If the property is missing, the latest version of the runtime will be added on the first run or build for Android.
* **tns-ios.version** - Specifies the version of the iOS runtime. If the property is missing, the latest version of the runtime will be added on the first run or build for iOS.

Here is an example of a basic main `package.json` file:

``` JSON
{
    "nativescript": {
        "id": "org.nativescript.myApplication",
        "tns-android": {
            "version": "6.1.2"
        },
        "tns-ios": {
            "version": "6.1.0"
        }
    },
    "description": "My NativeScript Application",
    "license": "MIT",
    "repository": "https://github.com/myApplication",
    "dependencies": {
        "nativescript-theme-core": "~1.0.6",
        "tns-core-modules": "~6.1.0"
    },
    "devDependencies": {
        "nativescript-dev-webpack": "~1.2.0"
    },
    "readme": "My NativeScript Application"
}
```

## The **hooks** Directory

The `hooks` folder exists only when the project depends on plugins that require a hook to function properly. Hooks are executable pieces of code or Node.js scripts that are used to alter or augment the behavior of an extendable NativeScript CLI command. For more information about hooks and how to use them in NativeScript, see [Extending the CLI](https://github.com/NativeScript/nativescript-cli/blob/master/extending-cli.md).

## The **tsconfig.json** File

The `tsconfig.json` file is present only in projects that use TypeScript. The file works as a guide during the [transpilation]({% slug transpilers %}) of TypeScript to JavaScript. You can fine-tune the transpilation process by configuring the various [compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html). For more information about `tsconfig.json`, see the official [TypeScript documentation](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

## The **nsconfig.json** File

The `nsconfig.json` is an optional configuration file, located at the root project directory on the same level as the main `package.json` file. This file makes it possible for users to modify the structure of their application. The available configurations are `appPath`, `appResourcesPath`, `overridePods` and `webpackConfigPath`.

The paths (`appPath`, `appResourcesPath`, `webpackConfigPath`) must be relative to the project root (where the `package.json` file and `platforms` directory are located) in order for everything to work as expected. If `appPath` is omitted, the CLI will assume the application files are located inside a folder called {% nativescript %}`app`{% endnativescript %}{% angular %}`src`{% endangular %} inside the project folder. If `appResourcesPath` is omitted, the CLI will assume that they are at their default location - a folder called `App_Resources` inside the folder containing the rest of the app files. The `webpackConfigPath` option allows you to specify the location of your webpack configuration file. If the value is not set, the CLI will use `webpack.config.js` file located at the root of the application. More information for `webpackConfigPath` option is available in [custom webpack configuration article](./tooling/custom-webpack-configuration).
The `overridePods` option tells the CLI to use the Cocoapods defined in the project's Podfile (inside `App_Resources/iOS/Podfile`) as a resolution in case pluginstry to use different versions of the same pod. For example, in case plugin A wants to use version 2.7 of `AFNetworking` pod and another plugin wants version 3.0 of the same pod, the build operation will fail. In this case, you can set the `overridePods` to true in your `nsconfig.json` and set version of the `AFNetworking` in your `App_Resources/iOS/Podfile`. CLI will use only this version of the pod and will omit the occurences from the plugins. All other pods from plugins will still be included in the application.

### **nsconfig.json** Path examples

Let's assume the project is located at `/d/work/myApplication`.

* The first and default option is to not have an `nsconfig.json` file inside your project. In this case, the app will be located at `/d/work/myApplication/app` and the resources at `/d/work/myApplication/app/App_Resources`. CLI will look for `webpack.config.js` file as the `webpackConfigPath` is not set and it will not override any pods versions as `overridePods` is false by default.

* The second option is to specify only the app directory. The example given below will result in an app located at `/d/work/myApplication/code/src` and resources at `/d/work/myApplication/code/src/App_Resources`.

  ``` JSON
  {
      "appPath": "code/src"
  }
  ```

* The third option is to specify only the app resources directory. The example given below will result in an app located at `/d/work/myApplication/app` and resources at `/d/work/myApplication/resources`.

  ``` JSON
  {
      "appResourcesPath": "resources"
  }
  ```

* The fourth option is to specify both the app folder and resources directories. The example given below will result in an app located at `/d/work/myApplication/code/src` and resources at `/d/work/myApplication/resources`.

  ``` JSON
  {
      "appPath": "code/src",
      "appResourcesPath": "resources"
  }
  ```

* You can set all of the properties:

  ``` JSON
  {
      "appPath": "code/src",
      "appResourcesPath": "resources",
      "webpackConfigPath": "my-custom.webpack.config.js",
      "overridePods": true
  }
  ```
