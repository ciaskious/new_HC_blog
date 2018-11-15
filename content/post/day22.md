---
title: "Day22: Traits"
date: 2018-10-31
tags: ["Scala"]
draft: false
---

Today I went back to _Scala for Impatients_ for good. First thing in the morning was the kata session. I felt at the end quite disappointed, as I it went worse than yesterday. After deleting the code yesterday, I was feeling confident about the next session. But every session is a white canvas, so today, as I started my choreography, I stepped on my new ideas and fell in a loop of simple and really stupid errors. But this showed how much more quicker I have to be at asking for help on stuff that I don't know (Javascript syntax) because then I end up panicking and doing nonsense just by changing randomly  the code.  

### Traits

Traits are similar to Java's interfaces and they are collections of methods and field. In languages that support multiple inheritance, you often meet the _**diamond problem**_. As you cannot extend more than one classes, I find traits a really interesting part of the book and in order to explain this concept,  I have an example about humans in my head:  

```
class justHuman extends humanPowers

class softwareEngineer extends justHuman with powersOfSE

class superCoder extends softwareEngineer with superPowersOfSE

class sleepySuperCoder extends superCoder{
  override def eatPoopSleep(): Unit = {
    println("I am a superCoder but I need sleep!")
  }
}


trait humanPowers{
  def eatPoopSleep() = println("I have all the typical human needs")
  def wearsClothes() = println("Most of the times I am wearing clothes!")
}

trait superPowersOfSE extends humanPowers{
  //overrides eatPoopSleep method
  override def eatPoopSleep(): Unit = { println("I NEVER SLEEP!") }
  def speedOfLight() = println("I run at the speed of light!")
  def isInvisible() = println("Nobody can see me...I am invisible!")
}

trait powersOfSE{

  def hasBackPain() = println("My back hurts all the time")

  def usesMultipleScreens() = println("One screen is never enough")
}


object justHuman{
  def main(args: Array[String]): Unit = {


    val Anastasia = new softwareEngineer
    val human = new justHuman
    val humanEngineer = new justHuman with superPowersOfSE  // Singletons can use traits too!!
    val superman = new superCoder
    val sleepyMan = new sleepySuperCoder

    human.eatPoopSleep()
    Anastasia.eatPoopSleep()
    superman.eatPoopSleep()
    sleepyMan.eatPoopSleep()
  }
}
```

Although it is a short example, it took me about an hour to do the mixins. I played with inheritance, which made it a little bit more challenging and got several compilation errors.

* Class _justHuman_ is the superclass. Every human being has an _eatPoopSleep_ function (I guess?) and wears clothes.

* Trying to make a _superCoder_ sleepy was a crazy (over)ride! I rewrote the traits several times. In the end, I created gradually a _sleepySuperCoder_ class and overrode the _eatPoopSleep_ method. ! 2 different eatPoopSleep methods would cause a compiler error !

* Like classes, traits also have constructors.
  * They are constructed from left to right.
  * Parent traits are constructed first.
  * If there is a common parent between multiple traits, it is not re-constructed.
  * They are executed after the superclass construction but before the subclass is constructed.

For example, in the _superCoder_ class `` class superCoder extends justHuman with superPowersOfSE ``, the constructors are executed as such.
1. The superclass: _softwareEngineer_
2. The parent trait: _humanPowers_
3. The first trait: _powersOfSE_
4. The second trait: _superPowersOfSE_ // So, it is not No5 in the order, as its parent trait (_humanPowers_) has been already constructed.
5. Finally, the subclass: _superCoder_

For now, this is all what my train of thought would bring as result of this chapter. I feel I even fixed some misunderstandings left from the inheritance chapter, regarding overriding methods :D


[Song of the day] (https://www.youtube.com/watch?v=PUdyuKaGQd4)
