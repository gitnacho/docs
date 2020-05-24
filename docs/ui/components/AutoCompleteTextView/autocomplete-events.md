---
title: Events
page_title: RadAutoCompleteTextView Events | Progress NativeScript UI Documentation
description: This page is dedicated to the events provided by the RadAutoCompleteTextView control.
slug: autocomplete-events
tags: radautocompletetextview, events, autocompletetextview, nativescript, professional, ui
position: 5
publish: true
---

# RadAutoCompleteTextView Events

In this article you are going to learn about the **RadAutoCompleteTextView's** events.
The event are designed to notify you whenever a particular action, in the workflow of the control, has happened. They are quite useful when it comes to executing logic based on the **RadAutoCompleteTextView's** state.

## Available Events

The **RadAutoCompleteTextView** control exposes these events:

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

<snippet id='autocomplete-events-xml'/>
<snippet id='autocomplete-events-ts'/>

## References

Want to see this scenario in action?
Check our SDK examples repo on GitHub. You will find this and many other practical examples with NativeScript UI.

* [Events Examples](https://github.com/NativeScript/nativescript-ui-samples/tree/master/autocomplete/app/examples/events)
