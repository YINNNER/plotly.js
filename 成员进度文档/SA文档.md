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

## Performance & Scalability Perspective

| Desired Quality       | The ability of the system to predictably execute within its mandated performance profile and to handle increased processing volumes |
| --------------------- | ------------------------------------------------------------ |
| Applicability         | Any system with complex, unclear, or ambitious performance requirements; systems whose architecture includes elements whose performance is unknown; and systems where future expansion is likely to be significant |
| Concerns              | Response time, throughput, scalability, predictability, hardware resource requirements, and peak load behavior |
| Activities            | Capture the performance requirements, create the performance models, analyze the performance models, conduct practical testing, assess against the requirements, and rework the architecture |
| Architectural Tactics | Optimize repeated processing, reduce contention via replication, prioritize processing, consolidate related workloads, distribute processing over time, minimize the use of shared resources, partition and parallelize, use asynchronous processing, and make design compromises |
| Problems and Pitfalls | Imprecise performance and scalability goals, unrealistic models, use of simple measures for complex cases, inappropriate partitioning, invalid environment and platform assumptions, too much indirection, concurrency-related contention, careless allocation of resources, and disregard for network and in-process invocation differences |

 	It's true that with the development of Internet and society, people rely heavier on software than ever before. Meanwhile, as the number of software users has been increasing dramatically, the concern of performance and scalability of certain software especially the software with a large number of users has been raised among a lot people.

​	This chapter discusses two related quality properties for large information systems: performance and scalability. These properties are important because, in large systems, they can cause more unexpected, complex, and expensive problems late in the system lifecycle than most of the other properties combined.

​	Intel chief Gordon Moore observed in 1965 that the processing power of computer chips doubled approximately every eighteen to twenty-four months
(now known as Moore’s Law). This remark seems to apply as much today as it  did  in  1965,  so  one  would  hope  that  by  now  performance  and  scalability would have receded as major concerns for most computer systems. Unfortunately, this isn’t the case, for a couple of reasons.

​	The most fundamental reason for performance concerns is that the tasks we  set  our  systems  to  perform  have  become  much  more  complex  over  time, and the demands we make on the systems (in terms of the complexity, number of transactions, number of users, and so on) have also grown in ways that would have been unimaginable in the 1960s.

​	To make matters worse, the performance of a computer system depends on much more than the raw processing power of its hardware. The way that hardware  is  configured,  the  way  resources  are  allocated  and  managed,  and the way the software is written can have significant impacts (good or bad) on the system’s ability to meet its performance goals. The simple fact is that we haven’t  become  much  better  at  managing  the  performance  of  our  systems since the 1960s—and we’ve actually gotten worse in some ways, such as our lack of attention to runtime memory use.

​	The scalability property of a system is closely related to performance, but rather  than  considering  how  quickly  the  system  performs  its  current  work- load, scalability focuses on the predictability of the system’s performance as the workload increases. Even if your system meets its goals today, how confident  are  you  that  it  still  will  in  the  future?  Will  it  be  able  to  cope  with  in- creased numbers of users, transactions, or messages? Will it be able to handle increased  complexity  of  processing?  How  will  it  behave  when  unexpectedly presented with a huge increase in workload? Applying the Performance and Scalability perspective to your architecture will help you answer all of these questions.	

​	We are going to discuss the performance and scalability of the powerful visualization software - Plotly, in several views as listed below.

| View        | Applicability                                                |
| ----------- | ------------------------------------------------------------ |
| Functional  | Applying this perspective may reveal the need for changes and compromises to your ideal functional structure to achieve the system’s performance requirements (e.g., by consolidating system elements to avoid communication overhead). The models from this view also provide input to the creation of performance models. |
| Information | The Information view provides useful input to performance models, identifying shared resources and the transactional requirements of each. As you apply this perspective, you may identify aspects of the Information view as obstacles to performance or scalability. In addition, considering scalability may suggest elements of the Information view that could be replicated or distributed in support of this goal. |
| Deployment  | Applying this perspective may result in changes to the concurrency design due to identifying problems such as excessive contention on key resources. Alternatively, considering performance and scalability may result in concurrency be- coming a more important design element to meet these requirements. Elements of concurrency views (such as interprocess communication mechanisms) can also provide calibration metrics for performance models. |
| Development | One of the possible outputs of applying this perspective is a set of guidelines related to performance and scalability that should be followed during software development. These guidelines will probably take the form of dos and don’ts (e.g., patterns and antipatterns) that must be followed as the software is developed in order to avoid performance and scalability problems later when it is deployed. You will capture this information in the Development view. |
| Operational | The application of this perspective highlights the need for performance monitoring and management capabilities. |

### Ⅰ：Concerns

#### Response Time

​	Response time is the length of time it takes for a specified interaction with the system to complete. For a human-oriented system, this could be the length of time between the user initiating the request and the response being available for her use (e.g., the time from clicking a user interface button to seeing the response screen populated with data). For an infrastructure-oriented system such as a database, this could be the time between invoking a service and the service  returning  a  response  (e.g.,  the  time  from  calling  a  query  application programming interface to obtaining the query results).

​	We define two broad classes of response times you may want to consider separately.

1. Responsiveness considers how quickly the system responds to routine
   workloads such as interactive user requests. The response time for such operations is typically in the order of a few seconds. The key consideration for such workloads is user productivity, ensuring that the system does not slow down its users.
2. Turnaround time is the time taken to complete (turn around) larger tasks.
   This is typically measured in minutes or hours, and the key considerations are whether the task can be completed in the time available to it and the impact the task has on the system responsiveness while it is running.

​       These  two  classes  of  response  times  can  affect  different  types  of  stake- holders and often require quite different technical solutions to make sure that requirements of each type are met.	

#### Throughput

​	Throughput is defined as the amount of workload the  system is capable of handling in a unit time period. Throughput and response time have a complex interrelationship  in  most  systems.  In  general,  the  shorter  your  transaction processing  time,  the  higher  the  throughput  your  system  can  achieve.  How- ever, as the load on the system increases (and throughput rises), the response time for individual transactions tends to increase. Therefore, it is quite possible to end up with a situation where throughput goals can be met only at the expense  of  response  time  goals,  or  vice  versa.

#### Scalability

​	Most systems are subject to workload growth in some form. Scalability is the ability of a system to handle this increased workload, which may be due to an increase in the number of requests, transactions, messages, or jobs the system is required to process per unit of time or an increase in the complexity of these tasks.

​	Long-term scalability always has an associated time element that considers how soon the increase in workload is anticipated to arrive. You may also need  to  consider  transient  scalability—that  is,  the  ability  to  handle  short bursts  of  increased  workload  (such  as  increased  traffic  to  an  Internet  news
site during an international crisis).

#### Predictability

​	In  addition  to  providing  acceptable  response  time  and  throughput,  another desirable property of a computer system is its ability to perform predictably. By this we mean that similar transactions complete in very similar amounts of time regardless of when they are executed. Similarly, the maximum transaction throughput the system can cope with should not vary significantly over time (in particular, it shouldn’t decrease).

​	Predictability is often a more desirable quality than absolute performance.

#### Hardware Resource Requirements

​	A  major  part  of  the  performance  and  scalability  puzzle  is  working  out  how much (and what type of) hardware your system will need, and this is usually an  early  concern  in  any  project,  being  captured  as  part  of  the  Deployment view. Hardware must be considered early because it costs money, takes time to acquire, often needs people to operate it, and often needs to be housed in purpose-built  environments.  The  amount  of  hardware  needed  for  a  system usually has a significant and very visible impact on its overall cost.

​	In general, more hardware means higher throughput and better response times, albeit at higher cost. Given this fundamental tension between cost and performance, your role is often to establish the minimum amount of hardware that will allow the system to meet its performance goals.	

------

### Ⅱ：Applying to Plotly.js

​	This section provides a detailed view on how the architecture of Plotly.js enables the development of highly scalable and performance as a visualization library.

#### Response Time

​	For the reason that Plotly.js is data visualization library generally used on web browser which is based on JavaScript language. So it's in fact Object-based and Event-driven. On top of that, it inherits many features from JavaScript like weak-typed, cross-platform and most importantly---fast.

​	Why can Plotly.js be so fast? I think there may be couples of reasons. Among these reasons there are good code structure and algorithms. These are actually grapes of wisdom of the Plotly.js contributors lol. However, I hold the view that the most significant reason lies in the intrinsic trait of JS. That is, as JavaScript's continuous dominance in the area of front end especially the web browser, an increasing number of web browser enterprises like Google Chrome and Firefox choose to modify their product  to improve the performance of their embedded JavaScript interpreters so that they can adapt JavaScript language better to get higher interpretation and running efficiency when coping with JS code, which also causes the change of programmers' attitude towards JavaScript who was in the past thought as inefficient and slow. So this trend leads to the great improvement of JavaScript running performance on the web browser, from which all the derived products benefit a lot, as well.

​	How much exactly do they benefit? We take the powerful JavaScript Engine--- Google V8 as an example. V8 engine made a great alteration for Interpretation of JS code, that is, it firstly compiles the JS code into machine code, then runs the machine code. In this way the browser doesn't have to interpret the JS codes every time running the codes .Instead, the repeated codes will be compiled into machine code in one time and since then be executed much faster.  Sometimes the running time can be shortened to even thousands of times.

​	This change is just like the introduction of JIT(Just in time compiler) in Java. From which the running efficiency of Java improved dramatically.

#### Throughput

​	As a relatively light-weight visualization library, there is actually nothing much to say about throughput. One thing we can say for sure is, most interaction(paragraphs of Plotly code  written on HTML) can be responded in a pretty short time.

#### Scalability

​	 As an open source visualization JS library, Plotly.js does pretty well in its scalability and maintainability.

​	Firstly, plotly supports users' customized graph types. Which means users can upload their own graph types(of course written in JavaScript). In fact, plotly.js comes with hundreds of types of graph congenitally, like Scientific graphs, revenue graphs, 3-D graphs.

![img](https://upload-images.jianshu.io/upload_images/3605636-23c3bc06aae3da9d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/554/format/webp)

​                                               ****example: uploaded graph type by netizen ****



![img](https://upload-images.jianshu.io/upload_images/3605636-9ef0db06f4be9550.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/554/format/webp)

​                               ****Click on certain entities on customized graph we can see the source code ****

​	So this feature dramatically increases the scalability of Plotly.js. It actually fosters a open source community for all netizen or programmers who are interested in visualization.

​	Secondly, it supports the editing of graphs interactively by your mouse or keyboard just like Excel. Just like the principle obeyed by many GUI editor : **what you see it exactly what you get**. When you edit the graph by dragging and clicking, the back end  will automatically generate the corresponding codes for you. For netizens who are not so proficient in programming but hold a enthusiastic heart for graphing and visualization, it will greatly motivates them to make some contributions to the Plotly Community.

#### Predictability

​	As for the predictability, thanks to the support from various kinds of favorable JS engines like Google v8, the processing time of repeated codes can be guaranteed in a very low level. Cuz most of your codes are the innate codes of Plotly.js library, so they will all be compiled into binary code, which can be processed in neglectable time.

​	So generally speaking, the predictability of Plotly's processing time is pretty certain and not too long.

#### Hardware Resource Requirements

​	One telling truth is, plotly.js doesn't require high-performance hardware at all. Since it's a visualization library based on JS and used in web browser, it's pretty light-weight. What's more, despite its versatile functionality, the implementation is actually not that complicated, which can be run in almost all platforms including PC, workshop, server, network.

​	As is mentioned above, lots of browsers have also made some effort to optimize the running efficiency of JS form code, so from the software perspective, it solve a lot of bottlenecks of Plotly's performance.

​	For the two reasons, nearly all users can use their device-no matter what kind of device it is, to get the graphs they want with some brief codes. what you need, are just a browser, a installed plotly.js plugin and of course, a keyboard

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

