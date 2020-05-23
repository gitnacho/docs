---
title: Donut
page_title: Donut Series | Progress NativeScript UI Documentation
description: This article gives a basic introduction of Donut series and continues with a sample scenario of how Donut series are used.
slug: chart-series-donut-angular
tags: series, cartesian, donut, angular, nativescript, professional, ui
position: 13
publish: true
---

# Chart Donut series

**DonutSeries** are a type of [ChartSeries]({% slug chart-series-overview-angular %} "Chart Series Overview") that use a circular statistical graphic, which is divided into slices to illustrate numerical proportion. In a donut chart, the arc length of each slice (and consequently its central angle and area), is proportional to the quantity it represents. They differ from **PieSeries** by the fact that they have a blank center in the the middle, making the chart resemble more a donut. The size of this blank center is determined by the value of the **innerRadiusFactor** property which accepts values between 0 and 1.

* [Setup](#setup)
* [Properties](#properties)
* [References](#references)

## Setup

To display a Donut Chart, you will need to:

* Add **RadPieChart** to your component.
* Add an instance of **DonutSeries** with the **tkPieSeries** directive and set its **items** property to a collection of data items and its **valueProperty** to the name of the property used to determine where to determine the proportion between the splices.

To illustrate this setup, let's create an example. Just like with all angular 'pages' let's start with the `Component` in which we will place our {% typedoc_link classes:RadCartesianChart %} instance. We create a basic angular `Component` that contains a collection of objects provided by an custom service, which will be used by the chart to provide intuitive data visualization. The service is a simple 'mock' of an backend call that will return an array of objects:

### Example 1: Define a data service

<snippet id='chart-angular-data-service'/>

Inside that service we have a single function which returns an array:

#### Example 2: Define a source with data

<snippet id='chart-angular-categorical-source'/>

<snippet id='chart-angular-country'/>

All that is left is to declare the template of the angular component in which we:

#### Example 3: Add chart to component's template

<snippet id='chart-angular-pie-series-component'/>
<snippet id='chart-angular-pie-series'/>

#### Figure 1: Chart with DonutSeries on Android (left) and iOS (right)

![Cartesian chart: Pie series](../../../../img/ns_ui/pie_series_android.png "Pie series on Android.") ![Cartesian chart: Pie series](../../../../img/ns_ui/pie_series_ios.png "Pie series on iOS.")

## Properties

* {% typedoc_link classes:PieSeries,member:outerRadiusFactor %} - This property can increase and decrease the diameter of the series. By default, it occupies the whole plot area and is equal to 1. Setting the outerRadius to 0.9 will decrease the radius of the series by 10 percent. Similarly, the value 1.1 will increase it. Leaving the property with value 1 will make the donut fill the available space.
* {% typedoc_link classes:PieSeries,member:expandRadius %} - This property defines the extent to which the selected pie segment is shifted. Again, this property is measured in percents. A value of 1.1 defines that the selected segment will expand by 10% of the pie radius.
* {% typedoc_link classes:PieSeries,member:startAngle %} and {% typedoc_link classes:PieSeries,member:endAngle %} - These properties are used to define the pie range. The `startAngle` sets the angle in degrees from which the drawing of the pie segments will begin.
Its default value is 0. The `endAngle` determines whether the chart will appear as a full circle or a partial circle. Its default value is 360 degrees.
* {% typedoc_link classes:DonutSeries,member:innerRadius %} - This property specifies the size of the blank center. The acceptable values are between 0 and 1.

## References

Want to see this scenario in action?
Check our SDK examples repo on GitHub. You will find this and many other practical examples with NativeScript UI.

Examples used in this article:

* [Pie Series Example](https://github.com/NativeScript/nativescript-ui-samples-angular/tree/master/chart/app/examples/series/pie)

Related articles you might find useful:

* [**Series Overview**]({% slug chart-series-overview-angular %})
* [**Pie Series**]({% slug chart-series-pie-angular %})
* [**Bar Series**]({% slug chart-series-bar-angular %})
