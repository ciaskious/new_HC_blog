---
title: "Day30: Trie to understand"
date: 2018-11-13
tags: ["Scala"]
draft: false
---

### How I ended up to tries today?

Well, I started my day motivated for week 3 on Coursera! During the lesson on class hierarchies, what actually got my attention were class extensions. My train of thought had to question and research many terms, so I will try to sum it all up here in this very short post.

### How-to-do-it vs Why-use-it

Although I have used class extensions before, sometimes is good to get back to things and pay attention to the detail. Although I didn't get something super new on the topic, somehow I feel like I am finally getting the point of "functional" and "immutability", and really understanding more on data structures; what opened my eyes was ``persistent data structures``, which were referred as the _cornerstone of scaling functional programming_ in the video. And what really made my day, was this [video](https://www.youtube.com/watch?v=Wo0qiGPSV-s) on tries. But first things first...

### Persistent? What are tries? Why do we care about immutability? How many times a day do pandas poop?

I want to avoid the "googlish-theoritical" stuff, so:  

* A data structure is **persistent** if, when changed, can still preserve its previous version *brain exploded*

* A trie ( pronounced like _try_) is a persistent, concurrent, tree-like data structure.

* They can be used for efficient information re **trie** val and common use case are dictionaries for predictive text (e.g. google search).

* ``Tries vs Hash Tables:`` They need no hash function, so no key collisions. Every key is unique as every path to a value is unique.  
  But it comes with a price -> sometimes search can get slow.  

And last but not least... Pandas can poop up to 40 times a day **#factOfTheDay**

I know that this is not a fascinating post on tries, but I am still trieng...  😅


[Song of the day] (https://www.youtube.com/watch?v=yTCDVfMz15M)
