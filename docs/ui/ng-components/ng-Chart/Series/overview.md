---
title: Overview
page_title: Series Overview | Progress NativeScript UI Documentation
description: An overeview of all series supported by Telerik Chart for NativeScript
slug: chart-series-overview-angular
tags: series, cartesian, pie, angular
position: 1
publish: true
---

# Chart Series Overview

If you followed the [getting started]({% slug chart-getting-started-angular %} "Chart Getting Started") article, you now know how to create a chart and add it to a NativeScript page. In this article, you will learn which are the available series and how to choose the most appropriate depending on the data that you want to plot. The NativeScript UI Chart comes with a bunch of series suitable for different types of data. When the data has be visualized on a cartesian coordinate system, the {% typedoc_link classes:RadCartesianChart %} should be used along with an instance of one of the {% typedoc_link classes:CartesianSeries %} subtypes. The other option is to use {% typedoc_link classes:RadPieChart %} with an instance of the {% typedoc_link classes:PieSeries %}. The `CartesianSeries` are additionally divided into two types: {% typedoc_link classes:ScatterSeries %} and  {% typedoc_link classes:CategoricalSeries %}.

* [Series Types](#series-types)
* [Selection](#selection)
* [Stack Mode](#stack-mode)
* [Styling](#styling)
* [Series Labels](#series-labels)
* [References](#references)

## Series Types

Here is a complete list of all series types:

* CategoricalSeries Presenting Discrete Data
  + **BarSeries**
  + **RangeBarSeries**
  + **BubbleSeries**
* CategoricalSeries Presenting Continuous Data
  + **LineSeries**
  + **SplineSeries**
  + **AreaSeries**
  + **SplineAreaSeries**
* CategoricalSeries Presenting Financial Data
  + **OhlcSeries**
  + **CandlesctickSeries**
* CartesianSeries Presenting Two Continuous Variables
  + **ScatterSeries**
  + **ScatterBubbleSeries**
* ChartSeries Presenting Numerical Proportion
  + **PieSeries**
  + **DonutSeries**

### ChartSeries Type

The **ChartSeries** is the base class for all series and provides the following properties:

* {% typedoc_link classes:ChartSeries,member:showLabels %} - Determines whether labels are shown for each data point.
* {% typedoc_link classes:ChartSeries,member:legendTitle %} - Determines the title which will be displayed in the legend for the current series.
* {% typedoc_link classes:ChartSeries,member:valueProperty %} - Determines the name of the property on the source object that will provide the value used to plot the object in the chart.
* {% typedoc_link classes:ChartSeries,member:items %} - Used to bind the series with a source of data items.
* {% typedoc_link classes:ChartSeries,member:selectionMode %} - Responsible for the selection mode of the series.
* {% typedoc_link classes:ChartSeries,member:labelStyle %} - Property of type PointLabelsStyle defining the style of the point labels.

### CartesianSeries Type

**CartesianSeries** is a subtype of **ChartSeries** and draw the data from the source in a Cartesian Coordinate System. The cartesian series can be used only with **RadCartesianChart**. Along with all **ChartSeries**'s properties, **CartesianSeries** also provide the following:

* {% typedoc_link classes:CartesianSeries,member:horizontalAxis %} -  Defines the horizontal axis used to setup the chart.
* {% typedoc_link classes:CartesianSeries,member:verticalAxis %} - Defines the vertical axis used to setup the chart.
* {% typedoc_link classes:CartesianSeries,member:paletteMode %} - Defines the mode for applying palettes.

### CategoricalSeries Type

**CategoricalSeries** is a subtype of **CartesianSeries**. They require that the **RadCartesianChart** they are added to, has one axis that is category axis and shows the specific categories being compared and one axis that is a value axis and represents a measured value. Along with all **CartesianSeries**'s properties, **CategoricalSeries** also provide the following:

* {% typedoc_link classes:CategoricalSeries,member:categoryProperty %} - Defines the name of the property on the data object which will be used to plot the object into the right category.
* {% typedoc_link classes:CategoricalSeries,member:stackMode %} - Defines how separate series are combined within a single chart.

### CategoricalSeries Presenting Discrete Data

Some of the **CategoricalSeries** are generally used to display relation between values in discrete categories, but they can also be used to visualize change over a period of time. These series are [BarSeries]({% slug chart-series-bar-angular %} "Chart BarSeries"), [RangeBarSeries]({% slug chart-series-range-bar-angular %} "Chart RangeBarSeries"), [BubbleSeries]({% slug chart-series-bubble-angular %} "Chart BubbleSeries").

#### Figure 1: Categorical Chart with discrete data on Android (left) and iOS (right)

![Chart series](../../../img/ns_ui/chart-css-bar-01-android.png "Discrete Data on Android.") ![Chart series](../../../img/ns_ui/chart-css-bar-01-ios.png "Discrete Data on iOS.")

### CategoricalSeries Presenting Continuous Data

Some of the **CategoricalSeries** are generally used to display how values change over a period of time, but they can also be used to connect the values in discrete categories. These series are [LineSeries]({% slug chart-series-line-angular %} "Chart LineSeries"), [SplineSeries]({% slug chart-series-spline-angular %} "Chart SplineSeries"), [AreaSeries]({% slug chart-series-area-angular %} "Chart AreaSeries"), [SplineAreaSeries]({% slug chart-series-spline-area-angular %} "Chart SplineAreaSeries").

#### Figure 2: Categorical Chart with continuous data on Android (left) and iOS (right)

![Chart series](../../../img/ns_ui/chart-css-line-01-android.png "Continuous Data on Android.") ![Chart series](../../../img/ns_ui/chart-css-line-01-ios.png "Continuous Data on iOS.")

### CategoricalSeries Presenting Financial Data

Some of the **CategoricalSeries** are used to display financial data, such as stock prices, etc. These series are [OhlcSeries]({% slug chart-series-ohlc-angular %} "Chart OhlcSeries") and [CandlesctickSeries]({% slug chart-series-candlestick-angular %} "Chart CandlesctickSeries").

#### Figure 3: Categorical Chart with financial data on Android (left) and iOS (right)

![Chart series](../../../img/ns_ui/chart-css-candlestick-01-android.png "Financial Data on Android.") ![Chart series](../../../img/ns_ui/chart-css-candlestick-01-ios.png "Financial Data on iOS.")

### CartesianSeries Presenting Two Continous Variables

**ScatterSeries** is a subtype **CartesianSeries**. They require that the **RadCartesianChart** they are added to, has two axes that are value axes. These series are [ScatterSeries]({% slug chart-series-scatter-angular %} "Chart ScatterSeries") and [ScatterBubbleSeries]({% slug chart-series-scatter-bubble-angular %} "Chart ScatterBubbleSeries").

#### Figure 4: Scatter Chart on Android (left) and iOS (right)

![Chart series](../../../img/ns_ui/chart-css-scatter-01-android.png "Scatter Chart on Android.") ![Chart series](../../../img/ns_ui/chart-css-scatter-01-ios.png "Scatter Chart on iOS.")

### ChartSeries Presenting Numerical Proportion

**CartesianSeries** is a subtype of **ChartSeries** and draw the data from the source in a way that resembles pie slices. They can be used only with **RadPieChart**. They are generally useful to display how some value relates to the whole value. These series are [PieSeries]({% slug chart-series-pie-angular %} "Chart PieSeries") and [DonutSeries]({% slug chart-series-donut-angular %} "Chart DonutSeries").

#### Figure 5: Donut Chart on Android (left) and iOS (right)

![Chart series](../../../img/ns_ui/chart-css-donut-01-android.png "Donut Chart on Android.") ![Chart series](../../../img/ns_ui/chart-css-donut-01-ios.png "Donut Chart on iOS.")

## Selection

The chart support selection of series and selection of data points. More information about this feature is available in [this article]({% slug chart-series-selection-angular %} "Chart Series Selection").

## Stack Mode

When more than one series is added to a RadCartesianChart they can be stacked together. [Here's]({% slug chart-series-stack-mode-angular %} "Chart Series Stack Mode") more about this feature.

## Styling

[This article]({% slug chart-series-styling-angular %} "Chart Series Styling") contains more information about how to use CSS or palettes to customize the series' appearance.

## Series Labels

The drawing of labels can be controlled through axis' `showLabels` property. More information about the labels is available in their dedicated [article]({% slug chart-series-labels-angular %} "Chart Series Labels").

## References

Want to see this scenario in action?
Check our [SDK Examples](https://github.com/NativeScript/nativescript-ui-samples-angular) repository on GitHub. You will find this and many other practical examples with NativeScript UI.

Examples used in this article:

* [Bar CSS Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/css)
* [Line CSS Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/css)
* [Candlestick CSS Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/css)
* [Scatter CSS Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/css)
* [Donut CSS Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/css)

Related articles you might find useful:

* [**Line Series**]({% slug chart-series-line-angular %})
* [**Pie Series**]({% slug chart-series-pie-angular %})
* [**Series Styling**]({% slug chart-series-styling-angular %})
