---
title: "Day12: First time I tested my code (no clickbait!)"
date: 2018-10-17
tags: ["scala"]
draft: false
---

![tdd](/images/test_meme.jpg)  
And it was about time. We are in the era of automation, in the times of CI and automated testing. I never cared about testing my code as a student and I never had to tbh. Until I did a real service during my internship and screwed up in production. Yeah, I tested in production for a while, until it worked! (#EPIC_FAILS)

TDD in my head seems like a very hard thing to do. This means -> CHALLENGE ACCEPTED  
I think that now is the ideal time to start learning TDD, as the exercises in the book are getting more computational and I feel more confident writing Scala code.  After reading and researching on TDD principals, I chose ScalaTest and a simple class I wrote on Monday to work with.

__Write a class **BankAccount** with methods **deposit** and **withdraw**, and a read-only property **balance** .__  

* I started writing my test with Flatspec. I explored FunSpec and FunSuite, as well and will show some tests with those implementations in future posts.

* The point was to start with the test and then write the functions in the class.

* The first test fails and this when you add functionality to your code.

* You wipe your sweat and re-run the test.

* For me it failed 1000 times because I had tons of typos, but in the end end it worked.

``` Scala
// /src/test/scala/BankAccountTest
import org.scalatest.{FlatSpec, Matchers}

class BankAccountTest extends FlatSpec with Matchers {
  val bankAcc = new BankAccount(80)
      "BankAccount Balance" should "remain the same" in {
        bankAcc.withdraw(90)
        bankAcc.currentBalance should be(80) }
       it should "subtract the amount requested" in {
         bankAcc.withdraw(60)
         bankAcc.currentBalance should be(20)
       }
        it should "add the amount deposited" in{
          bankAcc.deposit(40)
        bankAcc.currentBalance should be(60)
      }
}
```
```Scala
// /src/main/scala/BankAccount
class BankAccount (private var balance: Double){

  def withdraw(amount:Double){
    if (balance >= amount ) balance -= amount
    else println("Insufficient funds")
  }

  def deposit(amount: Double) { balance += amount}

  def currentBalance = balance
}
```
It was fun in the end, but it hurt a little bit at the beginning. But I commit to TDD for the next weeks, with baby steps for now ;)

[🎶 of the day](https://www.youtube.com/watch?v=nrIPxlFzDi0)
