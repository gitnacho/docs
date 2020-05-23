---
title: View modes
page_title: RadCalendar view modes | Progress NativeScript UI Documentation
description: This article explains how to set the RadCalendar's view mode  with Angular
slug: calendar-view-modes-angular
tags: calendar, angular, view, modes, nativescript, professional, ui
position: 5
publish: true
---

# RadCalendar View Modes

{% typedoc_link classes:RadCalendar %} supports the view modes exposed by the {% typedoc_link enums:CalendarViewMode %} enum. The following view modes are supported:

* {% typedoc_link enums:CalendarViewMode,member:Week %}
* {% typedoc_link enums:CalendarViewMode,member:Month %}
* {% typedoc_link enums:CalendarViewMode,member:MonthNames %}
* {% typedoc_link enums:CalendarViewMode,member:Year %}
* {% typedoc_link enums:CalendarViewMode,member:Day %}

To change the view mode of {% typedoc_link classes:RadCalendar %} you should use its {% typedoc_link classes:RadCalendar,member:viewMode %} property and set it to one of the aforementioned values.

<snippet id='angular-calendar-view-modes-html' />
