---
title: Overview
page_title: RadGauge Overview  | Progress NativeScript UI Documentation
description: An overview page of RadGauge for NativeScript. This article explains the most important things you need to know before using RadGauge.
slug: gauges-overview-vue
tags: radgauge, gauges, overview, Vue, nativescript, professional, ui
position: 0
publish: true
---

# RadGauge Overview

{% typedoc_link classes:RadGauge %} is a highly customizable component that allows you to show the current status of a value within a range of upper and lower bounds, illustrate progress towards a goal or a summary of a fluctuating metric.

## Figure 1: Radial gauge with indicators

![NativeScriptUI-Overview-iOS](../../../ui/img/ns_ui/gauges-gettingstarted-ios.png "RadRadialGauge in iOS") ![NativeScriptUI-Overview-Android](../../../ui/img/ns_ui/gauges-gettingstarted-android.png "RadRadialGauge in Android")

## Scales

{% typedoc_link classes:RadGauge %} supports multiple {% typedoc_link classes:GaugeScale %} objects. The scale has range and a set of indicators that are rendered according to the scale's range.

## Indicators

{% typedoc_link classes:GaugeIndicator %} is a visual element that points to or visualizes a range of values on a scale. Multiple indicators can be added to a scale. Indicators can be animated when their value is changed.

## Vue directives

When using the {% typedoc_link classes:RadGauge %} with Vue you are going to work with multiple custom Vue RadGauge specific directives. In short these directives are used by the Vue framework to enable 'linking' between separate HTML tags into one 'complex' element.

Here is a full list of the available custom Vue {% typedoc_link classes:RadGauge %} directives and components:

### Components

Represent the major elements:

| Selector          | Class (more details)                                  |
|-------------------|-------------------------------------------------------|
| RadRadialGauge | {% typedoc_link classes:RadRadialGaugeComponent %} |

### Directives

Represent the smaller elements that are visualized in {% typedoc_link classes:RadListView %}:

| Selector          | Class (more details)                                  |
|-------------------|-------------------------------------------------------|
| RadRadialGauge | The RadRadialGauge instance |
| RadialScale | The scale instance |
| RadialBarIndicator | The indicator instance |
| RadialNeedle | The needle instance |

<h3 id="directives">Directives</h3>

Represent the 'link' mechanism of the smaller with the major elements

| Selector          | Class (more details)                                  |
|-------------------|-------------------------------------------------------|
| tkRadialGaugeScales | Sets the scales of the RadRadialGauge |
| tkRadialScaleIndicators | Sets the indicators of the RadRadialGauge |
| tkRadialBarIndicatorStyle | Sets the indicatorStyle of the RadialBarIndicator |
| tkRadialGaugeTitleStyle | Sets the titleStyle of the RadRadialGauge |
| tkRadialGaugeSubtitleStyle | Sets the subtitleStyle of the RadRadialGauge |
| tkRadialNeedleStyle | Sets the needleStyle of the RadRadialGauge |
