---
title: "Day35: Unit Testing Intro"
date: 2018-11-20T13:28:31+01:00
tags: ["testing"]
draft: false
---

I decided to start my week with something different than Scala. I am still a total beginner at testing, so I picked Unit testing for starters. It is the only thing I knew about testing until I was introduced to TDD. But having tried to embrace TDD, when coding Katas for example, I was still confused. Am I doing Unit tests already? I just start with them first and :ta-da: TDD!

> Unit Testing refers to what you are testing, TDD to when you are testing.  

My question was triggered by the StackOverflow response above... I guess the answer would be yes and the comparison would be useless. I can start writing unit tests at the beginning, but it doesn't necessarily mean that you are doing TDD.
Letting the test drive you while coding, is a whole ritual and way of design. I have described  [here](https://ciatastrophe.netlify.com/2018/10/17/day12/) in plain words my first contact with TDD and I just got a #post_reflection_shock by reading it again after almost 3 weeks.   

Nothing new on Unit testing: you try to test the expected behavior of the smallest possible isolated parts (Units or SUT-System Under Test) of your code.

I have the impression that nobody paid attention to testing during University, because it was perceived as just a way to prove that your code works and not as a tool for improving it. And this is why nobody was in the mood for writing Unit tests after the main program was done.

### Mocking stuff

In order to test these individual Units, you sometimes have to mock parts of your code that make use of indirect I/O ( cannot be observed within the public interface - external files, API data, message queues, etc), slow down your code or don't even exist yet.
The terminology of this topic got a little bit messy and found many debates on their misuse. I will try to list and quickly explain my first findings below :  

``_Test doubles_`` is a general term that describes all the components mocked for test purposes. But there are different types of test doubles in the mocking world, all serving their own purposes. For example:   

``_Dummies_`` are carried around without having much meaning. They exist to make your code compile and will never be used ( for example they can be the mandatory parameters in order to create a new instance of a class).  

``_Stubs_`` override methods to return values that are predefined in the test (cannot return anything unspecified - for example when we want to avoid side effects from real-data). They have no functionality (no assertions, no verifications) and they do not record number of interactions.

``_Mocks_`` look like stubs, but they can make a test fail. Unlike stubs, they are _interaction-based_, so they have expectations from specific actions, which they also verify.  

``_Fakes_``... I have used them a lot while prototyping (_Fake it till u make it_); you actually fake part of functionality with an implementation, different - way simpler - than the final one in production.

``_Spies_`` are somehow a combi of mocks and stubs. They record method calls or other information related.

In the future I will try ScalaMock and Mockito in order to gain a better understanding of this topic.  

### #Deep_Days  

![deep bug](/images/deep_meme.jpg)[Source: testbytes.net](https://www.testbytes.net/blog/software-testing-memes/)  



[Song of the day] (https://www.youtube.com/watch?v=PEBS2jbZce4)
