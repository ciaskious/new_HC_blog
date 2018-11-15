---
title: "Day10: Lists, Classes and other Drugs"
date: 2018-10-15
tags: ["scala"]
draft: false
---

##  #Monday
Why? Why Monday? I opened my eyes hoping I am trapped in a Sunday's nightmare... but it was not a dream. It is Monday and I have to get my sh*t together for my next sprint.
It was not a bad week but I still need to work on my self organization when it comes to tasks and goals.  
So, I managed to finish the first 4 chapters of the book. I am very satisfied but I feel I need to practice more on the stuff I learn, because I have a fear that I will forget the details soon. I have to admit that I didn't invest as much time as I wanted on vim, but there is time to improve with small steps when I'll start working with tests in the next exercises and chapters of the book.  
In addition, I set up my IDE (Intellij) and now I am calm and happy again :)

On Friday though, I left something behind for this week's first post...

### Lists

Lists were not included in the 4th chapter but, as I said, the post was a recap on Data Structures.  
So, in 4 words: Lists are dynamic Arrays. But not exactly...
In Scala, lists are:  

* Immutable. The values of the elements cannot be modified.  
* Linked lists. This means we cannot do binary search, the elements have to be accessed sequentially.

They consist of nodes with two parts: One is the data field and the other one is a pointer to the next node.

Basic List operations:
```scala
scala> val foo = List(1, 2 ,3 ,4)
foo: List[Int] = List(1, 2, 3, 4)

scala> val bar = Nil // Create empty List
bar: scala.collection.immutable.Nil.type = List()

scala> foo.head
res1: Int = 1

scala> foo.tail
res2: List[Int] = List(2, 3, 4)

scala> foo.isEmpty
res3: Boolean = false

scala> bar.isEmpty
res4: Boolean = true
```

### Classes
Today I moved into classes, but it is a big chapter and I want to combine it with objects in order to write a detailed post with an example.
I am very excited so far, but it is only the beginning. Functional programming principles are not that far away... 👻

[🎶 of the day](https://www.youtube.com/watch?v=xdpcjtRW2jY)
