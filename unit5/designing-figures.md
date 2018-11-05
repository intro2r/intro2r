Encoding Values
==================


## The effective display of quantitative information involves two fundamental challenges


1. Best medium (table/graph type).

2. Designing graph to convey message.





Encoding Values in Graphs
=========================

Data graphics ~ verbal language

The rules of graphical communication are rarely arbitrary

Usually based on an understanding of visual perception:

1. How we see,

2. Visually encode information for easy and accurate decoding by audience.


## Most Graphs Are ...

 - 2D
 
 - 2 axes (horizontal, x; vertical, y)
 
 
Value-Encoding Objects
=====================

 - Points
 
 - Lines
 
 - Bars
 
 

## Points


 - Pinpoint specific location on graph,
 
 - Encode values associated with scale on each axis.
 
 - Shapes (dots, squares), filled/open.
 
 - YES: dot plot, strip plot, scatter plot.
 
 - NO: time series.
 


![](http://www.intro2r.info/unit5/img/designing-figures1.png)


## Lines

 - Lines connect points.
 
 - Encode values by location.
 
 - Ends of line segments mark values. 
 
 - Overall shape of data values.
 
 - Slope is meaningful.
 
 - YES: time series.
 


![](http://www.intro2r.info/unit5/img/designing-figures2.png)


## Points & Lines


 - Overall shape & individual values.
 
 - Multiple time series.
 
 - Lines should only connect points that are related/connected.
 


![](http://www.intro2r.info/unit5/img/designing-figures3.png)


## Bars

 - Encode values 2 ways:
 
   + location of end point,
   
   + length/height 

 - Easy to compare lengths to determine relative magnitude.
 
 - Discrete values, not connected.
 

![](http://www.intro2r.info/unit5/img/designing-figures4.png)



## Bars


 - Bars _can_ be used for connected values (e.g., time series) when:
 
   - you want to compare individual values at specific times, or
   - histogram
 
![](http://www.intro2r.info/unit5/img/designing-figures5.png)



### Bars need to start at zero




![](http://www.intro2r.info/unit5/img/designing-figures6.png)



![](http://www.intro2r.info/unit5/img/designing-figures7.png)


### In this case, points are better


![](http://www.intro2r.info/unit5/img/designing-figures8.png)




![](http://www.intro2r.info/unit5/img/designing-figures9.png)



 
# Relationships


### Time series 
 
Values change through time (e.g., $ per mo.)

 
### Ranking

Values ordered by size (e.g., sales, population)
 
 
### Part-to-Whole
 
Values represent parts/proportions of a whole (e.g., relative cover, regional sales)
 
 
### Deviation

Values represent the difference between two sets of values (e.g., income vs outgoing)



### Distribution
 
Counts of values per interval/bin (e.g., number of trees per size class)


### Correlation

Comparison of two paired sets of values (e.g., height vs weight)
 
 
### Geospatial
 
Values displayed on a map (e.g., population per city, species richness per site) 
 
 
### Nominal Comparison

Values are compared for unordered categories (e.g., regions, fruit type)


 - - -


## Graph Selection Matrix

![](http://www.intro2r.info/unit5/img/designing-figures10.png)

 - - -



