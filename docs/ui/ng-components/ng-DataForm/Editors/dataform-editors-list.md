---
title: Editors List
page_title: RadDataForm Editors List | Progress NativeScript UI Documentation
description: An article which lists the editors supported by RadDataForm for NativeScript and demonstrates their usage.
slug: dataform-editors-list-angular
tags: raddataform, editors, dataform, angular, nativescript, professional, ui
position: 1
publish: true
---

# RadDataForm Editors List

If you followed the [getting started]({% slug dataform-start-source-angular %} "RadDataForm getting started") section, you now know how to edit an object's properties with `RadDataForm` for NativeScript. The [editors overview]({% slug dataform-editors-overview-angular %} "Editors Overview in RadDataForm for NativeScript") page outlined the main features of the editors in `RadDataForm`. This article will demonstrate the supported editors and show you how to use them.

* [Complete List](#complete-list)
* [Editors by Usage](#editors-by-usage)

  + [Simple Text](#simple-text)
  + [Numeric](#numeric)
  + [True or False](#true-or-false)
  + [Date and Time](#date-and-time)
  + [Input from Predefined Lists](#input-from-predefined-lists)
  + [Input with AutoComplete Suggestions](#input-with-autocomplete-suggestions)
  + [View Only](#view-only)

* [Custom Editors](#custom-editors)
* [References](#references)

## Complete List

Here's the full list of the editors supported in {% typedoc_link classes:RadDataForm %}:

* {% typedoc_link enums:DataFormEditorType,member:Text %}: Simple text input.
* {% typedoc_link enums:DataFormEditorType,member:MultilineText %}: Text input, which supports more than one line.
* {% typedoc_link enums:DataFormEditorType,member:Email %}: Again for text input, with email optimized keyboard.
* {% typedoc_link enums:DataFormEditorType,member:Password %}: Masks the entered text.
* {% typedoc_link enums:DataFormEditorType,member:Phone %}: Again for text input, with phone optimized keyboard.
* {% typedoc_link enums:DataFormEditorType,member:Number %}: For input of numbers from the keyboard.
* {% typedoc_link enums:DataFormEditorType,member:Decimal %}: For input of numbers from the keyboard, supports decimal values.
* {% typedoc_link enums:DataFormEditorType,member:Switch %}: For boolean values.
* {% typedoc_link enums:DataFormEditorType,member:Stepper %}: For choosing a number by tapping on buttons to increase or decrease it.
* {% typedoc_link enums:DataFormEditorType,member:Slider %}: For choosing a number by sliding between the minimum and maximum values.
* {% typedoc_link enums:DataFormEditorType,member:Picker %}: For picking a value from a predefined list (drop-down list).
* {% typedoc_link enums:DataFormEditorType,member:SegmentedEditor %}: For picking a value from a predefined list (horizontal list).
* {% typedoc_link enums:DataFormEditorType,member:List %}: For picking a value from a predefined list (vertical list).
* {% typedoc_link enums:DataFormEditorType,member:DatePicker %}: For picking a date from a calendar.
* {% typedoc_link enums:DataFormEditorType,member:TimePicker %}: For picking a time from a clock.
* {% typedoc_link enums:DataFormEditorType,member:AutoCompleteInline %}: For picking single or multiple items from a suggestion list.
* {% typedoc_link enums:DataFormEditorType,member:Label %}: For simply displaying the property value inside a non-editable label.

## Editors by Usage

Here's more about each of the supported editors based on their common usage:

### Simple Text

The following editors can be used for properties of type `string`:

* **Text**: Provides text input with the default keyboard. It is default for properties of type `string`.

#### Figure 1: Text editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Text-Android](../../../img/ns_ui/dataform-editors-list-01-android.png "Text Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Text-iOS](../../../img/ns_ui/dataform-editors-list-01-ios.png "Text Editor in DataForm in iOS")

* **Password**: Masks the entered text

#### Figure 2: Password editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Password-Android](../../../img/ns_ui/dataform-editors-list-02-android.png "Password Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Password-iOS](../../../img/ns_ui/dataform-editors-list-02-ios.png "Password Editor in DataForm in iOS")

* **Phone**: Uses phone optimized keyboard.

#### Figure 3: Phone editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Phone-Android](../../../img/ns_ui/dataform-editors-list-03-android.png "Phone Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Phone-iOS](../../../img/ns_ui/dataform-editors-list-03-ios.png "Phone Editor in DataForm in iOS")

* **Email**: Uses email optimized keyboard.

#### Figure 4: Email editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Email-Android](../../../img/ns_ui/dataform-editors-list-04-android.png "Email Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Email-iOS](../../../img/ns_ui/dataform-editors-list-04-ios.png "Email Editor in DataForm in iOS")

* **MultilineText**: Supports more than one line.

#### Figure 5: MultilineText editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Multiline-Android](../../../img/ns_ui/dataform-editors-list-05-android.png "Multiline Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Multiline-iOS](../../../img/ns_ui/dataform-editors-list-05-ios.png "Multiline Editor in DataForm in iOS")

### Numeric

The following editors can be used for properties of type `number`:

* **Number**: For input of numbers from the keyboard. It is default for `number` properties on Android.

#### Figure 6: Number editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Number-Android](../../../img/ns_ui/dataform-editors-list-06-android.png "Number Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Number-iOS](../../../img/ns_ui/dataform-editors-list-06-ios.png "Number Editor in DataForm in iOS")

* **Decimal**: For input of numbers from the keyboard, supports decimal values. It is default for floating-point `number` properties on Android.

#### Figure 7: Decimal editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Decimal-Android](../../../img/ns_ui/dataform-editors-list-07-android.png "Decimal Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Decimal-iOS](../../../img/ns_ui/dataform-editors-list-07-ios.png "Decimal Editor in DataForm in iOS")

* **Stepper**: For choosing a number by tapping on buttons to increase or decrease it. It is default for `number` properties on iOS.

#### Figure 8: Stepper editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Stepper-Android](../../../img/ns_ui/dataform-editors-list-08-android.png "Stepper Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Stepper-iOS](../../../img/ns_ui/dataform-editors-list-08-ios.png "Stepper Editor in DataForm in iOS")

* **Slider**: For choosing a number by sliding between the minimum and maximum values. It is default for floating-point `number` properties on iOS.

#### Figure 9: Slider editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Slider-Android](../../../img/ns_ui/dataform-editors-list-09-android.png "Slider Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Slider-iOS](../../../img/ns_ui/dataform-editors-list-09-ios.png "Slider Editor in DataForm in iOS")

### True or False

* **Switch**: Uses a switch to get true/false input. It is default for `boolean` properties on iOS.

#### Figure 10: Switch editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Switch-Android](../../../img/ns_ui/dataform-editors-list-10-android.png "Switch Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Switch-iOS](../../../img/ns_ui/dataform-editors-list-10-ios.png "Switch Editor in DataForm in iOS")

> Note that on Android the default editor for `boolean` properties is **CheckBox** which is not supported on iOS.

### Date and Time

The **DatePicker** and **TimePicker** editors can be used to pick a date or time. They support values of type `Date` and values of type `string` in the following formats: `yyyy-MM-dd` for `DatePicker` and `HH:mm` for `TimePicker`. The value that is committed when edited with these editors will be in the same format as the initial value of the edited property. If the initial value is `null` or is of type `Date`, then the committed value will be of type `Date`. If the initial value is `””` (empty string or string in the supported formats), the committed value will be `string` in the supported formats.

* **DatePicker**: For picking a date from a calendar.

#### Figure 11: DatePicker editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-DatePicker-Android](../../../img/ns_ui/dataform-editors-list-11-android.png "DatePicker Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-DatePicker-iOS](../../../img/ns_ui/dataform-editors-list-11-ios.png "DatePicker Editor in DataForm in iOS")

* **TimePicker**: For picking a time from a clock.

#### Figure 12: TimePicker editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-TimePicker-Android](../../../img/ns_ui/dataform-editors-list-12-android.png "TimePicker Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-TimePicker-iOS](../../../img/ns_ui/dataform-editors-list-12-ios.png "TimePicker Editor in DataForm in iOS")

### Input from Predefined Lists

The following editors can be used for properties of any type but they need to have their acceptable values defined through a value provider. [Here]({% slug dataform-editors-providers-angular %} "Value Providers in RadDataForm for NativeScript")'s an article with more information about the value providers.

* **Picker**: For picking a value from a drop-down list.

#### Figure 13: Picker editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Picker-Android](../../../img/ns_ui/dataform-editors-list-13-android.png "Picker Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Picker-iOS](../../../img/ns_ui/dataform-editors-list-13-ios.png "Picker Editor in DataForm in iOS")

* **SegmentedEditor**: For picking a value from a horizontal list.

#### Figure 14: SegmentedEditor editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-SegmentedEditor-Android](../../../img/ns_ui/dataform-editors-list-14-android.png "SegmentedEditor Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-SegmentedEditor-iOS](../../../img/ns_ui/dataform-editors-list-14-ios.png "SegmentedEditor Editor in DataForm in iOS")

* **List**: For picking a value from a vertical list.

#### Figure 15: List editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-List-Android](../../../img/ns_ui/dataform-editors-list-15-android.png "List Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-List-iOS](../../../img/ns_ui/dataform-editors-list-15-ios.png "List Editor in DataForm in iOS")

### Input with AutoComplete Suggestions

* **AutoCompleteInline**: For text input with option to choose single or multiple items from a suggestions list.

#### Figure 16: AutoCompleteInline editor in Tokens mode on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-AutoCompleteInline-Android](../../../img/ns_ui/dataform-editors-list-16-android.png "AutoCompleteInline Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-AutoCompleteInline-iOS](../../../img/ns_ui/dataform-editors-list-16-ios.png "AutoCompleteInline Editor in DataForm in iOS")

This editor also uses a predefined list with values, but they are not the only acceptable values, but rather they are suggestions that are displayed when the user starts typing for the keyboard. There are two modes: {% typedoc_link enums:AutoCompleteDisplayMode,member:Plain %} and {% typedoc_link enums:AutoCompleteDisplayMode,member:Tokens %}. The desired mode should be set to the {% typedoc_link classes:EntityProperty,member:autoCompleteDisplayMode %} property of the `EntityProperty`. The `Plain` mode can be used for `string` properties, while the `Tokens` mode can be used for properties of type `string[]`. The next code snippet shows how you can setup the `AutoCompleteInline` editor. The source object is of type `Booking` and has two properties: `from` and `to`. The `from` property is of type `Array<String>` and we use the `AutoCompleteInline` editor with `Tokens` display mode, which allows us to select multiple items from our suggestions. The `to` property is of type `string` and we use the `AutoCompleteInline` editor with `Plain` display mode which allows us to type a simple text.

#### Example 1: Use the AutoCompletInline editor in Plain and in Token modes

<snippet id='angular-dataform-autocomplete-html'/>

#### Figure 17: AutoCompleteInline editor in Plain mode on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-AutoCompleteInline-Android](../../../img/ns_ui/dataform-editors-list-17-android.png "AutoCompleteInline Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-AutoCompleteInline-iOS](../../../img/ns_ui/dataform-editors-list-17-ios.png "AutoCompleteInline Editor in DataForm in iOS")

### View Only

* **Label**: For simply displaying the property value inside a non-editable label.

#### Figure 18: Label editor on Android (left) and iOS (right)

![NativeScriptUI-DataForm-Editors-Label-Android](../../../img/ns_ui/dataform-editors-list-18-android.png "Label Editor in DataForm in Android") ![NativeScriptUI-DataForm-Editors-Label-iOS](../../../img/ns_ui/dataform-editors-list-18-ios.png "Label Editor in DataForm in iOS")

## Custom Editors

If an editor that you would like to use is not included in the list with predefined editors, you can provide your own native view that will be used with the existing editor logic. You can read more [here]({% slug dataform-editors-custom-angular %} "RadDataForm custom editors").

## References

Want to see this scenario in action?
Check our [SDK Examples for Angular](https://github.com/NativeScript/nativescript-ui-samples-angular) repo on GitHub. You will find theis and many other practical examples with NativeScript UI.

* [Editors Common Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/dataform/app/examples/editors)
* [Editors AutoComplete Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/dataform/app/examples/editors/autocomplete)
* [Editors Labels Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/dataform/app/examples/editors/labels)

Related articles you might find useful:

* [**Custom Editors**]({% slug dataform-editors-custom-angular %})
* [**Value Providers**]({% slug dataform-editors-providers-angular %})
