---
title: Getting Started
page_title: RadGauge Getting Started  | Progress NativeScript UI Documentation
description: A getting started page of RadGauge for NativeScript. This article explains the steps to create RadRadialGauge from scratch.
slug: gauges-gettingstarted
tags: radgauge, gauges, gettingstarted, nativescript, professional, ui
position: 1
publish: true
---

# RadGauge Getting Started

This article will guide you through the process of adding a {% typedoc_link classes:RadRadialGauge %} instance to a page in a {N} application and adding scales and indicators to it. The code snippets from this section are available as [a standalone demo application](https://github.com/NativeScript/nativescript-ui-samples).

#### Figure 1. Radial gauge with needle and bar indicators
![NativeScriptUI-Getting-Started-iOS](../../img/ns_ui/gauges-gettingstarted-ios.png "RadRadialGauge in iOS") ![NativeScriptUI-Getting-Started-Android](../../img/ns_ui/gauges-gettingstarted-android.png "RadRadialGauge in Android")

## Installation
Run the following command to add the plugin to your application:

```
tns plugin add nativescript-ui-gauge
```

## Adding a RadRadialGauge to Your Page

Then, in order to add a {% typedoc_link classes:RadRadialGauge %} instance in a page of your application, you need to define the following XML namespace:

* `xmlns:gauge="nativescript-ui-gauge"`.

Here's how to add a {% typedoc_link classes:RadGauge %} instance to your page:

#### Example 1: Add a RadRadialGauge to your page.
<snippet id='gauges-getting-started-add' />

## Adding Scale with Indicators

To display data the {% typedoc_link classes:RadRadialGauge %} instance is not enough. We should add also add a scale with at least on indicator. In this example we are going to add a {% typedoc_link classes:RadialScale %} with several {% typedoc_link classes:RadialBarIndicator %} instances and one {% typedoc_link classes:RadialNeedle %}. To add a scale to the {% typedoc_link classes:RadRadialGauge %} we should use its {% typedoc_link classes:RadGauge,member:scales%} property. Adding indicators to the scale is similar - we are using {% typedoc_link classes:RadialScale %}'s {% typedoc_link classes:GaugeScale,member:indicators%} property.

#### Example 2: Add a scale with indicators to the gauge.
<snippet id='gauges-getting-started-add-scale-indicators' />

## References
Want to see this scenario in action?
Check our SDK examples repo on GitHub. You will find this and many other practical examples with NativeScript UI.

* [Getting Started Example](https://github.com/NativeScript/nativescript-ui-samples/tree/master/gauge/app/examples/getting-started)

Related articles you might find useful:

* [**Indicators**]({% slug gauges-indicators %})
* [**Scales**]({% slug gauges-scales %})
