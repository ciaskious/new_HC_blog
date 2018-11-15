---
title: "Day7: (H)Array"
date: 2018-10-10
tags: ["scala"]
draft: false
---

### Scala arrays... Java arrays

Arrays...I was excited! I am impatient as the book implies and I was looking forward to some trouble. Actually, the trouble's so big that I don't even feel like writing about it.  

> _But as I am sure that soon after practicing I will be laughing at these days, I will write about it! In a few words..._

Having used arrays mostly in Java and C++, it is very interesting to see the differences now in Scala.

First things first:

```scala
//Initialize an array
val a = new Array[Int](3)  instead of int[] a = new int[3];
```
But what's interesting about it:
When I create a Scala array, in the JVM it is implemented as a Java array.   
For example:
```scala
val b = Array("hello", "there!") // Scala
String[] = {"hello", "there!"}   // Java
```
In addition, the previous chapter introduced the _for comprehensions_ . It is a _loop_ type, where a new collection(s) of values is generated. It was in the "advanced _for_ loops" category and yesterday tbh, it felt pretty advanced.
But today, a very nice example was given in the book. It came to me as a surprise, how this is implemented.

> Suppose we want to remove all negative elements from an array buffer of integers.

A possible solution in a Java approach for the array _a_ could be:
```java
public static int rmNegatives(int[] a) {
    int i = 0;
    for(int j = 0; j < num.length; j++) {
       if(num[j] >= 0) {
           a[i++] = a[j]; //holding out all negative elements
       }
    }
}
```

The book shows a similar sequential way in Scala. Then, another way is suggested using a _for comprehension_ :
```scala
val positionsToKeep = for (i <- a.indices if a(i) >= 0) yield i
for (j <- positionsToKeep.indices) a(j) = a(positionsToKeep(j))
a.trimEnd(a.length - positionsToKeep.length)
```

This way you keep and copy the positions of the non-negative elements and then you shorten the buffer. Boom!

Moreover, Scala arrays can be passed to your Java code, as soon as the elements are of the same type. In Scala, automatic type conversion is forbidden. But if you have an Array on the Scala side and you treat it as an array of objects in Java, this works fine.

The comment section is open for thoughts and corrections :D

I felt the need to get back to vim at some points but it would be just an excuse for not doing the exercises at the end of the chapter... 😅  

[🎶 of the day](https://www.youtube.com/watch?v=4fqwVBuunxY)
