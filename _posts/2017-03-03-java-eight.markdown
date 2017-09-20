---
layout: post
title:  "Java 8"
date:   2017-03-03 13:34:00 -0500
categories: cliffsnotes java
---

### Java 8 ###

Main differences of Java 8 from Java 7:

 - Lambdas
 	- More succinct than  Runnables & Anonymous classes
 	- Can use method references
 - Streams
 	- Collection Support, Optional (e.g. null handling)
 	- Common Operations (filtering, sorting, skipping, etc.)
 	- Early Termination (shortcutting)
 	- Parallelization
 - Functional Interfaces
   - Predicates (Boolean valued functions that take one argument, plus the logic operations)
   - Functions (Take one argument, produce a result)
   - Suppliers (Produce a result of a given type- no arguments)
   - Consumers (Void functions that operate on one argument)
   - Comparators (with new default methods, reverse, thenOrdering, etc.)
 - Date/Time handling
   - Joda Creator's Joda Time created a Java API to handle time properly
   - Handles ZonedDateTimes vs local date time (or instants)
   - Handles Subtle differences: Durations & Periods, Zones vs ZoneOffset
     + Period (a period of time) that can change based on calendar variations
       (DST, February vs March, LeapYear, etc.)
     + Duration (an exact amount of time) doesn't change based on variations
     + ZoneId (where you are)
     + ZoneOffset (difference from GMT which can change in a given zone due to DST)
   - DateTimeFormatter (pre-defined standards, plus system defaults, plus custom)
   	 + used for both formatting & parsing
   - Richer API
   	 +  now(), with(), plus(), minus(), etc.
   	 + comparisons/evaluations: before(), after(), isLeapYear()
 - Completable Future (similar to promises in javascript)
 	 - easy waiting to run the next step based on an asynchronous result
 	 - chaining/logic of multiple asynchronous functions
 - Nashorn (Javascript code can be run/tested in JVM)


### Streaming Operations ###
  - Some methods on streams are _terminals_ - meaning no more streaming will occur.  (_forEach_ is the most common terminal)
  - Sort (persents a sorted VIEW of the data, does not manipulate the back-end data)
  - Map - Transforms element X into Y by mapping it.  This is one to one.
  - Matching (anyMatch, allMatch, etc.)
  - Limit - stop after a certain amount.
  - Count - (a terminal) that counts the elements
  - Reduce - (a terminal) that reduces output
  - Collect - (a terminal) that folds data/repackages it into a different form

*Best Practices*
  - Avoid infinite streams
  -

### Collectors ###

  - toList (convert all the elements to a list)
  - toSet  (convert the elements to a set)
  - toCollection (convert the elements into a particular *non-immutable* collection)
  - toMap (to a map) done with a _keyMapper_ and a _valueMapper_
  	+ to handle collisions a 3rd argument can be introduced which allows you to choose between two values
  - collectingAndThen - takes a collection and applies a finishing transformation to it.
  	+ used to make things immutable/unmodifiable (after the collection is built)
  - joining (used on string streams) to join elements (with optional pre & post strings & separators)
  - counting (returns a long- count of the elements in the stream)
  - summarizing(Int/Long/Double)  - returns average/count/min/max/sum for the given collection elements.
    + averaging(Int/Long/Double), summing(Int/Long/Double), max..., etc. operations are individually available.
  - groupingBy() - Produces a MAP where the values are a collection
    + the key/classifier function is used to determine what key to use for the given values.
    + the value collection is given by another Collector (defaults toList)
    + Note the value need not be a collection if the Collector used is a reduction (summarizing, reducing, etc.) collector
  - partitioningBy() - splits all values based on a predicate into either the Boolean.TRUE or Boolean.FALSE key.
  - or a custom collector -- implement the Collector<T,A,R> interface.
    + T = the type of input elements to the reduction operation
    + A = the mutable accumulation type of the reduction operation (often hidden as an implementation detail)
    + R = the result type of the reduction operation






### Sources ###
  - [Pro Java 8]
  - [5 Java 8 Features] that will change how you code
  - [Why you should upgrade to java 8]
  - [Java 8 Tutorial]
  - [Java 8 Collectors]

[Pro Java 8]: http://www.apress.com/us/book/9781484206423
[5 Java 8 Features]: http://blog.takipi.com/5-features-in-java-8-that-will-change-how-you-code/
[Why you should upgrade to java 8]: https://www.toptal.com/java/why-you-need-to-upgrade-to-java-8-already
[Java 8 Tutorial]: http://winterbe.com/posts/2014/03/16/java-8-tutorial/
[Java 8 Collectors]: http://www.baeldung.com/java-8-collectors
