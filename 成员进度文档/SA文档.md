[TOC]

# Plotly.js - The open source JavaScript graphing library

![plotly_2017-9160501](images/plotly_2017.png)

##  Abstract

Built on top of d3.js[[1]](#1) and stack.gl, plotly.js is a high-level, declarative charting library. plotly.js ships with over 30 chart types, including scientific charts, 3D graphs, statistical charts, SVG maps, financial charts, and more.[[2]](#2) The open source project that started in 2015 now has 16018 commits, 112 releases made by 101 different contributors on Github. While the development is open-source, the amount of documentation about contributing is limited. This results in a project where programming is not done through conventions or guidelines but with a strong foucus on getting things to work. Therefore, this document as a whole can serve as a helpful introduction to prospectives developers looking to better understand the architecture to which thay might contribute.

## Table of Contents

- [Introduction](#Introduction)
- [Stakeholders](#Stakeholders)
- [Context View](#Context View)
- [Functional View](#Functional View)
- [Development View](#Development View)
- [Evolution Perspective](#Evolution Perspective)
- [Technial debt](#Technial debt)
- [Conclusion](#Conclusion)
- [Reference](#Reference)

## Introduction

As we enter the era of big data, data analysis and data visualization technologies become particularly important. This increase demands an easy-to-use softeware to create sophisticated, interactive charts. Plotly is a technical computing company headquartered in Montreal, Quebec, that develops online data analytics and visualization tools. Plotly provides online graphing, analytics, and statistics tools for individuals and collaboration, as well as scientific graphing libraries for Python, R, MATLAB, Perl, JavaScript, Julia, Arduino, and REST[[3]](#3). As shown in Figure 1, Plotly offers a wide range of wonderful products of data analytics and visualization in different languages.

![屏幕快照 2018-10-10 16.29.24](images/屏幕快照 2018-10-10 16.29.24.png)

*Figure 1: Products of Plotly*

Every major company in Science, Engineering, and Finance is moving their software to the Web. Plotly provides the Web data visualization technology supporting this trend. Therefore, plotly's product for javascript, Plotly.js creates sophisticated, interactive charts in JavaScript for finance, engineering, and the sciences.

This document gives an overview of the overarching architecture of the plotly.js project. It sets the scens by introducing the project and discussing its stakeholders. It then takes on different viewpoints and perspectives as defined by Rozanski and Woods [[4]](#4) to analyse Plotly.js's performance, in addition to discussing the technical debt hidden in the depths of the codebase.

## Stakeholders

## Context view

### System scope & responsibilities

### External entities & interfaces

## Functional View

According to Rozanski and Wood's book [[3]](#3),

> Describes the system’s functional elements, their responsibilities, interfaces, and primary interactions. A Functional view is the cornerstone of most ADs and is often the first part of the description that stakeholders try to read. It drives the shape of other system structures such as the information structure, concurrency structure, deployment structure, and so on. It also has a significant impact on the system’s quality properties such as its ability to change, its ability to be secured, and its runtime performance. 

In this part, main functionalities are discussed, and the functional capabilities, external interfaces and internal struture are concerned.

### Functional capabilities

Functional capabilities define what the system is required to do and whate it is not required to do[[3]](#3).  Since Plotly.js strives to create sophisticated, interactive charts, the main functionalities that it needs to have coincide with that. Table 1 shows the core functionality required of Plotly.js and describes what their responsibilities are.

| Functionality       | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| Create chats        | The main component of the system is to create chats. Plotly.js can create different types of chats for finance, engineering, and the sciences. It has 5 major categories: baisc chats, statistical chats, scientific chats,  financial chats, maps and 3D chats. See all types of chats in Figure 2. |
| Static image export | Users can save plotly graphs to static images and view them in the browser. Plotly supports jpg, png and svg image export. |
| Responsive layout   | By setting plotly.js`config` to `{ responsive: true }`, plots will be resized upon changing the size of the window. This is especially useful for mobile devices switching from portrait to landscape. |
| Reat component      | Users can use react-plotly.js[[5]](#5) to embed D3 charts in your React-powered web application. This React component takes the chart type, data, and styling as Plotly JSON[[6]](#6) in its data and layout props, then draws the chart using Plotly.js. |
| Transforms          | Users can use Plotly.js to do transforms like filter, groupby, aggregations and multiple transforms combining these transforms together. |
| Custom controls     | Users can use Plotly.js to do custom controls like dropdown events, button events, slider events, lasson selection and range slider and selector. |
| Custom chart events | Users can use Plotly.js to do custom chat events like click events, hover events, zoom events and disable zoom events. |
| Animations          | Users can use Plotly.js to do many animations like baisic animations, adding sliders to animations, filled-area animation and map animation. |

![plotly.js JavaScript Graphing Library](images/plotly.js JavaScript Graphing Library.png)

### External interfaces

External interfaces are the data, event, and control flows between your system and others.[[3]](#3)The ecternal interfaces provided by Plotly.js mainly concern functinality to extension development possible. Among other things the functinality concerns plotting, layout, export  and so on. There are too many interfaces to completely list them in this report, so for a full list of available external interface refer to the [API](https://github.com/plotly/plotly.js/tree/master/src/plot_api). As an example of what is provided, table 2 shows a few of accessable inerfaces.

| API file     | Description                                                  |
| ------------ | ------------------------------------------------------------ |
| to_image.js  | Export plotly graphs to static image in different types.     |
| validate.js  | Validate a data array and layout object.                     |
| template_api | create a template off an existing figure to reuse style attributes on other figures. |

*Table 2: Examples of external interfaces*

### Internal structure

In the section on the development view, different modules of plotly.js is described. Each of the different functionalities belongs to different modules, which are as follows:

==待定==

## Development View

### Module Organization

### Standardization of Design

### Standardization of testing

### Codeline organization

## Security Perspective

## Performance & Scalability Perspective

## Technial debt

### SonarQube anlysis

### Testing debt

### Debt evolution

## Conclusion

## References

1. Data-Driven Documents.org. http://d3js.org/, 2018.
2. Plotly.js. https://plot.ly/javascript/, 2018.
3. Nick Rozanski and Eoin Woods. Software Systems Architecture: Working with Stakeholders using Viewpoints and Perspectives. Addison-Wesley, 2012.
4. Wikipedia.Plotly. https://en.wikipedia.org/wiki/Plotly, 2018.

5. Github.Reat-plotly.js. https://github.com/plotly/react-plotly.js, 2018.
6. Plotly JSON. https://help.plot.ly/json-chart-schema/, 2018.

