---
title: Display modes
page_title: RadAutoCompleteTextView Display Modes | Progress NativeScript UI Documentation
description: This page is dedicated to the Display Modes provided by the RadAutoCompleteTextView control.
slug: autocomplete-display-modes-vue
tags: radautocompletetextview, displaymodes, vue, nativescript, professional, ui
position: 3
publish: true
---

# RadAutoCompleteTextView Display Modes

**RadAutoCompleteTextView** has two predefined display modes.

* {% typedoc_link enums:AutoCompleteDisplayMode,member:Plain %}
* {% typedoc_link enums:AutoCompleteDisplayMode,member:Tokens %}

Display mode can be changed with the {% typedoc_link classes:RadAutoCompleteTextView,member:displayMode %} property of the **RadAutoCompleteTextView**. The default value is {% typedoc_link enums:AutoCompleteDisplayMode,member:Plain %}.

The next code snippet shows how to change that default value to {% typedoc_link enums:AutoCompleteDisplayMode,member:Tokens %}:

<snippet id='autocomplete-token-vue'/>

## Plain mode
In plain mode the {% typedoc_link classes:RadAutoCompleteTextView %} displays chosen item as plain text. With this mode only one item can be chosen.

## Tokens mode
Tokens mode allows multiple choice of items, which are displayed as tokens.

When **RadAutoCompleteTextView**'s `displayMode` is `Tokens`, you can apply two different behaviors for token arrangement.

* {% typedoc_link enums:AutoCompleteLayoutMode,member:Horizontal %}
* {% typedoc_link enums:AutoCompleteLayoutMode,member:Wrap %}

The layout mode of the tokens can be changed with the {% typedoc_link enums:RadAutoCompleteTextView,member:layoutMode %} property. The default value of this property is {% typedoc_link enums:AutoCompleteLayoutMode,member:Wrap %}.

<snippet id='autocomplete-layouts-wrap-vue'/>

### Wrap layout
In wrap mode tokens are arranged on multiple lines. Every time a new line is started the **RadAutoCompleteTextView** is expanding in order to show all tokens.

### Horizontal layout
In horizontal mode tokens are displayed on single line which can be scrolled horizontally in order to display all tokens.

## References

Related articles you mind find useful:

* [**Completion Modes**]({% slug autocomplete-completion-modes-vue %})
* [**Suggest Modes**]({% slug autocomplete-suggest-modes-vue %})
