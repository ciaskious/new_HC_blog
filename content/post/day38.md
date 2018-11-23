---
title: "Day38: Team Driven Development"
date: 2018-11-23T12:20:18+01:00
tags: ["apprenticeship"]
draft: false
---

I haven't posted since Tuesday, so I am not sure if it is day 38 or if it even matters. What really matters is that I learned something totally out of my league!   

I decided to join Masha as she was following the red book ( Functional Programming in Scala), a book that really terrifies me to be honest. This is why I wanted to do the online course first; I felt this would be somehow "easier" than deep diving into the book. But when it came up during the daily, that she would learn how a property-based testing library can be designed, I got carried away by the challenge and asked to join the learning process. I had no idea what property-based testing is - it is a whole different way of thinking.    

> The common unit tests are example-based tests. If they seemed hard to you, property-based tests will drive you insane.  

They are supposed to make your code bulletproof, as they testing every possible edge case. A property is a possible behavior in your code that you want to test. In contrast to unit tests, where you do several certain assertions based on a certain input and output, you define a whole range of possible inputs and generate repeatedly an exhaustive number of random test cases in order to reassure that your property will always have a certain output. It feels awesome because of the certainty they give you but consume a lot of time. It was also hard to think cases I take for granted.   
For example, for a sum method given a list _List(x,y,z,p,q)_, a possible property could be   
```
 sum(List(x,y,z,p,q)) == sum(List(x,y)) + sum(List(z,p,q))
```  
Addition is associative and since primary school, I have been taking this for granted!  

So that was good, but when we began the chapter on how to design such a library, I discovered so many gaps and as a result we ended up reading about "pure functional state". Well, that was a massive stroke! We spent these 2 days to read through the whole chapter and complete the exercises. I definitely loved the pairing part and although I am still scared of the book, I feel more confident and less stupid than on Wednesday 😅 If I were to go through this chapter alone, I would definitely have learned so much less in a very depressing way!  

In addition, I tried to keep my promise and dockerize finally a scala app. I started refreshing my knowledge on akka http and created a basic "hello blahblah". My plan was to do it in a team and use the sbt native packager, as I have used it in the past and found it very handy. Unfortunately, due to (ridiculous) technical issues I failed to make things work and I will finish it next week.  

Overall, my week began with doubts and some hopes...but here it comes to an end with much more confidence and food for thought on unexpected topics.

[Song of the day] (https://www.youtube.com/watch?v=-J7J_IWUhls)
