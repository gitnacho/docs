---
title: Getting started
page_title: RadCalendar Getting started | Progress NativeScript UI Documentation
description: This article is a short description and summary of RadCalendar's features and their usage with Angular
slug: calendar-getting-started-angular
tags: calendar, overview, angular, nativescript, professional, ui
position: 2
publish: true
---

# Getting Started with RadCalendar for Angular

This article will guide you through the process of adding a RadCalendar in your application. For more information on how each separate feature of {% typedoc_link classes:RadCalendar %} is used, please refer to the dedicated articles. The code snippets from this section are available as [a standalone demo application](https://github.com/NativeScript/nativescript-ui-samples-angular).

## Installation

Run the following command to add the plugin to your application:

``` Shell
tns plugin add nativescript-ui-calendar
```

## Adding a RadCalendar to Your Template

Before proceeding, make sure that the {% typedoc_link classes:NativeScriptUICalendarModule %} from the *nativescript-ui-calendar* plugin has been imported in an `ngModule` in your app. For example:

``` TypeScript
import { NativeScriptUICalendarModule } from "nativescript-ui-calendar/angular";

@NgModule({
    schemas: [NO_ERRORS_SCHEMA],
    imports: [
        ....
        NativeScriptUICalendarModule,
        ....
    ],
    declarations: [
        ....
    ]
})
export class CalendarExamplesModule { }
```

[Demo](https://github.com/NativeScript/nativescript-ui-samples-angular/blob/master/calendar/app/calendar/calendar-examples.module.ts).

To add a {% typedoc_link classes:RadCalendar %} in an Angular template you need to use `<RadCalendar></RadCalendar>` tag. The following code snippet demonstrates how to display a {% typedoc_link classes:RadCalendar %} in your application:

<snippet id='angular-calendar-getting-started' />

> {% typedoc_link classes:RadCalendar %} must be put in a parent layout panel that does not require from its children to have their own desired size. You should not therefore put {% typedoc_link classes:RadCalendar %} in a `StackLayout` or an auto-sized row within a `GridLayout`.
