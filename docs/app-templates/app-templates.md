---
title: NativeScript Application Templates
description: Learn more about the available application templates used as a blueprint for a NativeScript mobile application - SideDrawer, Tabs, Master-Detail
position: 70
slug: nativescript-application-templates
---

# NativeScript Application Templates

## Introduction to Application Templates

The NativeScript app template is a blueprint for a fully functional mobile application developed with NativeScript. The templates maintained by the NativeScript team reside in [GitHub](https://github.com/nativescript/nativescript-app-templates). Each template is also published as an npm package (e.g. [NativeScript Core with TypeScript Master Detail Template](https://www.npmjs.com/package/tns-template-master-detail-ts)).

There are several available templates that can help you bootstrap your NativeScript application using the best coding practices, in all supported flavors, including Angular & TypeScript, Vue, Vanilla JavaScript or TypeScript.

To create a new app using one of the templates, you can use the following command:

``` Shell
tns create my-app-name --template tns-template-name
```

> **Tip**: All of the app templates listed here are also available in [NativeScript Sidekick](https://www.nativescript.org/nativescript-sidekick). In addition, Sidekick offers cloud-based builds for iOS and Android, plugin management, app store publishing, and single page templates.

In the command above `tns-template-name` should be the template you wish to use. See bellow for the name of each template.

> Different versions of NativeScript can have different code in the application templates. If you create an app using an older version of the framework you might get less features from the ones included in the current NativeScript release.

## Blank

<img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-blank/tools/assets/appTemplate-ios.png" style="height:400px;border:1px solid black"> <img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-blank/tools/assets/appTemplate-android.png" style="height:400px;border:1px solid black">

{% nativescript %}

`tns-template-blank` - JavaScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-blank>
`tns-template-blank-ts` - TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-blank-ts>{% endnativescript %}{% angular %}
`tns-template-blank-ng` - Angular with TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-blank-ng>

{% endangular %}

A basic template with a single page and no custom styles. Useful for when minimal and clean code is needed.

## Navigation Drawer

<img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-drawer-navigation/tools/assets/appTemplate-ios.png" style="height:400px"> <img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-blank/tools/assets/appTemplate-android.png" style="height:400px">

{% nativescript %}

`tns-template-drawer-navigation` - JavaScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-drawer-navigation>
`tns-template-drawer-navigation-ts` - TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-drawer-navigation-ts>{% endnativescript %}{% angular %}
`tns-template-drawer-navigation-ng` - Angular with TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-drawer-navigation-ng>

{% endangular %}

This template contains a preconfigured {% nativescript %}[SideDrawer]({% slug sidedrawer-overview %}){% endnativescript %}{% angular %}[SideDrawer]({% slug sidedrawer-overview-angular %}){% endangular %} component from [NativeScript UI's built-in components]({% slug components %}) with several pages.

## Tabs

<img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-tab-navigation/tools/assets/phone-tab-ios.png" style="height:400px"> <img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-tab-navigation/tools/assets/phone-tab-android.png" style="height:400px">

{% nativescript %}

`tns-template-tab-navigation` - JavaScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-tab-navigation>
`tns-template-tab-navigation-ts` - TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-tab-navigation-ts>{% endnativescript %}{% angular %}
`tns-template-tab-navigation-ng` - Angular with TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-tab-navigation-ng>

{% endangular %}

This template uses a [TabView](https://docs.nativescript.org/cookbook/ui/tab-view) component for navigation. It also includes several pages to show how to populate the tabs and perform the navigation.

## Master Detail with Firebase

<img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-master-detail-kinvey/tools/assets/phone-masterDetail-ios.png" style="height:400px"> <img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-master-detail-kinvey/tools/assets/phone-masterDetail-detail-ios.png" style="height:400px">

{% nativescript %}

`tns-template-master-detail` - JavaScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail>
`tns-template-master-detail-ts` - TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail-ts>{% endnativescript %}{% angular %}
`tns-template-master-detail-ng` - Angular with TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail-ng>

{% endangular %}

This Master-Detail template is a fundamental building block for any app that displays a collection of objects and their details, which also need to work both in online and offline mode. It utilizes [Firebase](https://firebase.google.com/) as a backend.

## Master Detail with Kinvey

<img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-master-detail/tools/assets/phone-masterDetail-ios.png" style="height:400px"> <img src="https://raw.githubusercontent.com/NativeScript/nativescript-app-templates/master/packages/template-master-detail/tools/assets/phone-masterDetail-detail-ios.png" style="height:400px">

{% nativescript %}

`tns-template-master-detail-kinvey` - JavaScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail-kinvey>
`tns-template-master-detail-kinvey-ts` - TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail-kinvey-ts>{% endnativescript %}{% angular %}
`tns-template-master-detail-kinvey-ng` - Angular with TypeScript
Github repo: <https://github.com/NativeScript/nativescript-app-templates/tree/master/packages/template-master-detail-kinvey-ng>

{% endangular %}

This template is functionally identical to [Master Detail with Firebase](#master-detail-with-firebase). The only difference is that it utilizes [Kinvey](https://www.kinvey.com/) as a backend.
