### <mark style="background: #AD21D9;">Performance:</mark>  

With more and more apps being developed on Android devices performance is starting to matter to users  

Even through the latest devices have much more horsepower available to them  

In this lecture we will explore some things that can improve the performance of your applications  

To make them run faster, smoother and respond quicker

### <mark style="background: #AD21D9;">Why Performance matters:</mark> 

<mark style="background: #AD21D9;">Performance matters for two main reasons:</mark>  
1. Higher performance means a smoother more Instantaneous application that responds quickly to user input  
2. Apps that exhibit higher performance on the same tasks will complete in a shorter time meaning there is less use of the battery  

Thus it is in your interest to make your applications perform well

### <mark style="background: #AD21D9;">The two basic rules of performance:</mark>  

There are two basic rules to improving performance  
1. Don’t do work that is unnecessary  
2. Avoid memory allocation/deallocation wherever possible  

By observing these rules you will create an application that shows high performance and will place little drain on the battery

### <mark style="background: #AD21D9;">Code Profiler:</mark>  

Most of the performance numbers that you will see here have come from experimentation on Android code  

Code profiler  
- A tool for monitoring execution time of code. A profiler will produce a range of statistics that will show where a program spends the majority of its time.  

Gives an indication as to where the code can be improved to produce extra performance  

<mark style="background: #AD21D9;">Android Profiler:</mark>  
https://developer.android.com/studio/profile/android-profiler.htm

![](https://i.imgur.com/Fycs6Io.png)

![](https://i.imgur.com/blhallc.png)

### <mark style="background: #AD21D9;">Bottlenecks:</mark> 

When performing optimisation, must remember the law of diminishing returns  

Each subsequent optimisation will result in diminishing performance gain  

<mark style="background: #AD21D9;">Goal:</mark> only do optimisation to the point where performance is perceived as being good enough  

This is because you don’t remove bottlenecks in code you simply move them elsewhere

### <mark style="background: #AD21D9;">Memory Allocation/Deallocation - Avoid</mark>  

Memory allocation/deallocation are expensive operations in any OS  

Require a switch from user mode to kernel mode to allocate the memory and another switch back to continue running the application  

Also the more you allocate memory, the more the garbage collector will get involved and will reduce application performance  

There are a couple of examples involving string buffers and parallel single dimension arrays that can help reduce allocation

### <mark style="background: #AD21D9;">The Layout Inspector:</mark>

![](https://i.imgur.com/0Hodh7K.png)

### <mark style="background: #AD21D9;">An Example hierarchy:</mark> 

<mark style="background: #AD21D9;">For the purposes of an example:</mark>  
1. We will use a couple of linear layouts to represent the item that we have shown below  
2. We will use a vertical linear layout for the textviews on the right  
3. And that will be contained in a horizontal linear layout that will have an image on the left

![](https://i.imgur.com/9xKSniQ.png)

### <mark style="background: #AD21D9;">Layout Flattening:</mark> 

A hierarchy like this takes some time to build This will add up significantly if something like this is used in a list view  

Thus flattening this layout to two levels with a relative layout instead of a three level linear layout hierarchy would be beneficial  

An example of a revised layout is shown on the next slide

![](https://i.imgur.com/kCHbvTw.png)

### <mark style="background: #AD21D9;">include and merge:</mark>  

Very simple trick to reduce size of XML code. If you identify component combinations that are frequently reused – split into separate files  

And including them in each layout by using the ``<include/>`` tag  

Each reused layout should have the ``<merge/>`` tags as the root tag  

This way they will be included into the layout without any additional items in its place  

https://developer.android.com/training/improving-layouts/reusing-layouts.html

### <mark style="background: #AD21D9;">Battery Optimisation:</mark>  

In general your applications should try to use as little battery of a device as is possible  

Remember these devices generally last a day at best  

Thus applications that consume battery will be removed quickly  

It is possible however, to modify the behaviour of your application in response to changes in charging state or battery level

### <mark style="background: #AD21D9;">Battery - Determining & Monitoring Charging State</mark>

By registering an intent filter that looks for the ``ACTION BATTERY CHANGED`` intent you can determine information about the charging state  

Will enable you to not only determine if the  
device is charging  

But also if it is charging via USB or from AC  

For example you might ramp up performance when connected to AC than when on Battery or USB.

Using another intent filter it is possible to determine if the battery level is low or if it is ok  

Generally when a battery level goes low, it is good practice to reduce use of resources in application  
  
Enables device to minimize power as possible when the battery level is >=15%

### <mark style="background: #AD21D9;">Battery Levels and Charging States - Responding:</mark>

Good applications will do this when they have been informed that the battery level of the device is low. Some example actions include  
- Reducing the sample rate on sensors to consume less battery power  
- Disabling some functionality entirely e.g. disable access to flash with low power  

If the application is not critical to the system or user then all functionality may be disabled to save power

### <mark style="background: #AD21D9;">Final Optimisations:</mark>

If you must implement an algorithm that is not found in the standard libraries  
- Implement in the most efficient way possible  
- More efficiency == less battery drain  

If know what operations application is expected to mostly do, then use data structures that provide fast implementations of common operations i.e. know your collections!!  

Reduce the amount of work application has to do