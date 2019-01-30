---
title: "Day74: Design Principles (SOLID)"
date: 2019-01-29T11:01:46+01:00
tags: ["solid", "design"]
draft: false
---
Software Design: A category in my learning curriculum that I have neglected a bit. One more key to maintainable and extendable code (the other one was testing). I started with the Functional paradigm hand in hand with the Object Oriented. Then last week I devoted time to get to know better the SQL and noSQL differences. Today I started reading on SOLID, one of the design principles that Uncle Bob includes in his book on clean architecture. But let's break it down:  

# `[S]ingle Responsibility Principle`  

  > A class should have one, and only one, reason to change.

A thing to consider always when writing code. Giving your entities (module, class, function, etc) one and only responsibility (aka. a famiy of functions), reduces complexity, dependencies, side-effects and makes the code more likely to be used again in the future.     
The book class example [here](https://code.tutsplus.com/tutorials/solid-part-1-the-single-responsibility-principle--net-36074) is quite extensive but helped me understand a little bit about bussiness logic. So, there are many examples and use cases but they all mean one thing: **don't put in the same class functions that serve different purposes | change for different reasons!**

# `[O]pen/Closed Principle`   

  > You should be able to extend a classes behavior, without modifying it.

Open to new behaviors, but closed to any modification. Easy to say...  
If you give it more time you might think the same as I did; it looks like this goes hand-in-hand with SRP above. If you give your class only one reason to change, you don't give space for further modifications. No extra recompilations in case of a new feature. Ideal.. Doable? Maybe not 100%, as it depends on the level of abstraction you can give to your code.

## `[L]iskov Substitution Principle`   

  > Derived classes must be substitutable for their base classes.

A little tricky. Your derived class should provide as much as to be able to replace the base class. An instance of a class _Bird_ with a method _fly_, should cause no problems if it were substituted by an instance of its subclass _Pigeon_.
## `[I]nterface Segregation Principle`  

  > Make fine grained interfaces that are client specific.  

At this point all these "rules" start to look the same to me looking at basic implementation (animals, cars, printers, etc.). But as a noob I guess I have time to see real problem solving code and understand. Or someone can show me a litlle bit sooner... Or better I will ask myself! But feel free to comment good resources below.

## `[D]ependency Inversion`  

  > Depend on abstractions, not on concretions.
  > High-level modules should not depend on low-level modules. Both should depend on abstractions.

 Reaching this last one, I still have the feeling that everything is so connected to each other and fairly they all parts of a SOLID principal. I am also glad that I was driven by the Scala book to follow this without even realising it. I had a look at [some older examples](https://ciatastrophe.netlify.com/2018/10/31/day22/) that I came up with to judge them based on this last principle. And it feels like the traits did the job, but I can do better.

I loved this dive into SOLID because it gave me a better understanding of abstraction importance.  

Resources:   

* [Scala you are always on my mind <3](https://blog.knoldus.com/solid-principles-with-scala/)
* [Becoming a better developer by using the SOLID design principles by Katerina Trajchevska](https://www.youtube.com/watch?v=rtmFCcjEgEw)  
* [This article](https://blog.cleancoder.com/uncle-bob/2014/11/24/FPvsOO.html) from Uncle Bob gave a first answer to my question about these design principles being implemented in Functional Programming:  
`The fact that you’ve decided to use a language that doesn’t have an assignment operator does not mean that you can ignore the Single Responsibility Principle; or that the Open Closed Principle is somehow automatic. The fact that the Strategy pattern makes use of polymorphism does not mean that the pattern cannot be used in a good functional language. [4] | [4] A good functional language is one that allows for convenient polymorphism. Clojure is a good example.`  

* [A talk from Uncle Bob that I wish I had watched earlier](https://www.youtube.com/watch?v=TMuno5RZNeE)  

[Song of the day](https://www.youtube.com/watch?v=H3T1wVewVmQ)
