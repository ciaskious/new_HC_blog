---
title: "Day21: Katas"
date: 2018-10-30
tags: ["katas", "Scala"]
draft: false
---
It has been almost a week away from my Scala book. Yes, I missed it! Implementing some of the basics was o.k. but I was lacking basic concepts that really slowed me down with Exercism. I had a look at the community solutions and some of them were really genious. But as all the exercises are tagged with the concepts they use, I decided it is time to go back to theory and fill some gaps.

But before that, the day started with a Kata :) To be honest, I fist heard about them here at HolidayCheck. Katas are an important part of martial arts - as found in Wikipedia "Kata, a Japanese word, are detailed choreographed patterns of movements practiced either solo or in pairs.". Well this is somehow the case for software katas, as well.

> Coding Katas are all about practicing the craftsmanship.

You practice and repeat alone or in a team on an exercise, trying to improve, do it faster or even change languge/framework and on each iteration. For me personally, it is the most fun part of the day so far. It gives me freedom for experimentation on something new ( e.g. Javascript, which I hate but when I do it in the group it is actually fun because I don't focus on the language itself). Katas are getting me one more baby step closer to TDD and collaboration with my peers.

I am sad that I missed many of these sessions, but I am becoming slowly a morning person (long story) and getting here on time for them. I am really curious to see how much benefit I can get out of them in a longterm period of time. For now, I feel more confident after finishing a small piece of it; it works like a white canvas, you can start any way you want and be creative.

After refactoring, everything looks so understandable, it gets you hooked on the next test and the next AND THE NEEXT AND NEEEEXT....

![kata](/images/kata.jpg)  

 Today, I got an amazing idea from my peer while solving the [string calculator](http://osherove.com/tdd-kata-1/) kata. At some point we had to split a string like "1\n2,3", extract the numbers and treat '\n' and ',' as delimiters. And what would be shorter than a regex? Just a single ``split(/\D/)`` and you got both the delimiters! WAAAT? I am so excited that even understood the tiny regex. Baby steps seem to work!

Anyway, this was a Scala day. I went on with collections and it was mostly confirming most of what I implemented on exercism, so i don't feel inspired to blog about it. Tomorrow I will continue to case classes and Options, with which I have struggled before and it is time to solve the misunderstanding ;) I made a joke today about Options but I forgot about it already. I promise it was funny...


[Song of the day] (https://www.youtube.com/watch?v=40tS5WB-j-c)
