---
title: "Day9: TGIF and Data Stuctures"
date: 2018-10-12
tags: ["scala"]
draft: false
---

### val daysOfTheWeek = Map("Friday" -> "YAY")

Today lots of things got clear in my head: Tuples, Maps, Lists and Arrays. It was about time, as since university times all I have worked with is [(H)Arrays](https://ciatastrophe.netlify.com/post/day7/) and today it was a nice opportunity to recap while reading chapter 4.

So here is a general overview of data structures in Scala.
### **Array**
As we all know, arrays are fixed-sized collections, where collections of elements of the same type are stored. In an array of potatoes, there is no room for carrots. We can traverse the values and its indices. The elements are stored side-by-side and

``` scala
for ( day <- daysOfTheWeek ) { println(day)}
for ( i <- 0 to daysOfTheWeek.length) { println(day)}
```
However, you can create dynamic arrays and modify their size by using an _Array Buffer_

### **Tuple**
A general rule is, that you create a tuple when you want your function to return more that one value. It was one of the lessons I learned during my coding interview at HolidayCheck!  
A tuple is an immutable sequence of values, that don't have to be of the same type:
``` scala
scala> val myTuple = ( 1, 2.3, "Anastasia" )
myTuple: (Int, Double, String) = ( 1, 2.3, "Anastasia" )
```
 Unlike arrays, the positions in a tuple start from 1 instead of 0 :
 ```scala
 scala> myTuple._1
 res0: Int = 1
 ```
 The tuple is a very fast data structure, doesn't consume much memory and as it has a fixed size, it could replace the static Array.

### **Map**
Maps are collections of key-value pairs, where every pair is a tuple with n=2. They are immutable by default, so the pairs cannot be changed.
```Scala
scala> val immuTable = Map( 1 -> "Monday", 2 -> "Tuesday",  3 -> "Wednesday")
immuTable: scala.collection.immutable.Map[String,Int] = Map(Monday -> 1, Tuesday -> 2, Wednesday -> 3)

scala> immutable(2)
res1: String = Tuesday

scala> immuTable += ( 4 -> "Thursday")
  <console>:13: error: value += is not a member of scala.collection.immutable.Map[Int,String]
    Expression does not convert to assignment because receiver is not assignable.
         immuTable += ( 4 -> "Thursday")
```

To construct a mutable map:
```Scala
scala> val familyAges = collection.mutable.Map("mom" -> 48, "dad" -> 52, "sister" -> 28)
familyAges: scala.collection.mutable.Map[String,Int] = Map(sister -> 28, dad -> 52, mom -> 48)

//now you add new pairs
scala> familyAges += ( "grandma" -> 98 )
res3: familyAges.type = Map(sister -> 28, dad -> 52, grandma -> 98, mom -> 48)
```
In Scala, Maps are by default implemented as hash tables and as a result, the elements are arranged in an unpredictable order. The alternatives are the _LinkedHashMap_ - so that you visit the keys in insertion order,  or _SortedMap_ - a [TreeMap](https://www.scala-lang.org/api/2.9.2/scala/collection/immutable/TreeMap.html), where the keys are returned in sorted order.

```Scala
scala> val familyAges = scala.collection.mutable.SortedMap("mom" -> 48, "dad" -> 52, "sister" -> 28)
familyAges: scala.collection.mutable.SortedMap[String,Int] = TreeMap(dad -> 52, mom -> 48, sister -> 28)

scala> familyAges += ( "grandma" -> 98 )
res4: familyAges.type = TreeMap(dad -> 52, grandma -> 98, mom -> 48, sister -> 28)

scala> val familyAges = scala.collection.mutable.LinkedHashMap("mom" -> 48, "dad" -> 52, "sister" -> 28)
familyAges: scala.collection.mutable.LinkedHashMap[String,Int] = Map(mom -> 48, dad -> 52, sister -> 28)

scala> muTable += ( "grandma" -> 98 )
res5: muTable.type = Map(mom -> 48, dad -> 52, sister -> 28, grandma -> 98)
```

### Lists

This post already took more time than expected, so I will add lists as a treat in the Monday's post. ;)
Now, TGIF beer is waiting for me and the rest of the apprentices <3
Bis Monntag :D

[🎶 of the day](https://www.youtube.com/watch?v=mGgMZpGYiy8)
