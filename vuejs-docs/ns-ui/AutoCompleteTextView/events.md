---
title: Events
page_title: RadAutoCompleteTextView Events | Progress NativeScript UI Documentation
description: This page is dedicated to the events provided by the RadAutoCompleteTextView control.
slug: autocomplete-events-vue
tags: radautocompletetextview, events, vue, nativescript, professional, ui
position: 5
publish: true
---

# RadAutoCompleteTextView Events

In this article you are going to learn about the {% typedoc_link classes:RadAutoCompleteTextView %} events.
The events are designed to notify you whenever a particular action, in the workflow of the control, has happened. They are quite useful when it comes to executing logic based on the {% typedoc_link classes:RadAutoCompleteTextView %} state.

## Available events

The {% typedoc_link classes:RadAutoCompleteTextView %} control exposes these events:

* `tokenAdded` - triggered whenever a token is added.
* `tokenRemoved` - triggered whenever a token is removed.
* `tokenSelected` - triggered whenever a token is selected.
* `tokenDeselected` - triggered whenever a token is deselected.
* `textChanged` - triggered whenever the `text` property is changed.
* `didAutoComplete` - triggered whenever an item from the suggestions list is selected.
* `suggestionViewBecameVisible` - triggered whenever the suggestion view is shown.

All of these have identical logical structure and identical workflow, the only difference between them is the event which they are observing and notifing you about.

## Usage

In order to get notified when one of the above-mentioned events occur, you should use the following structure with the type of event you want to capture.

<snippet id='autocomplete-events-vue'/>
