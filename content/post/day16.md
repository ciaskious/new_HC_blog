---
title: "Day16: Exercism †"
date: 2018-10-23
tags: ["scala"]
draft: false
---


It was about time I took a brake from the Scala book. I finished the chapter on Inheritance with the exercises, hugged it and then left it aside for this week, cold and lonely. Although in theory, sooner or later I get what I am reading, just writing examples inspired by the book, is not enough for complete comprehension of the concepts. So, I joined the Scala track on [Exercism](https://exercism.io/) and did today my first exorcises.  

![exorcism](https://media.giphy.com/media/xT0BKoKdVxnrYBSGNq/giphy.gif)  
[via GIPHY](https://gph.is/20SBGwE)

So far, I find amazing! The exercises are given with the tests already, so I feel blessed now that I am trying TDD!   
The installation is super easy, there is no need for details in the post. There is also the opportunity to have a mentor, publish your solutions and get comments. My general issue with coding is that I overthink about my solutions and most of the times I do terrible tiny mistakes (most of the times in loops #shame_shame ).  

These small exercises work like a charm  for my complicated brain. I had time only for a couple, but it was already a good reason to get pen, paper and combine some of the stuff I learned from the book. For example, the exercise [_Multiple of Sums_](https://github.com/exercism/scala/tree/master/exercises/sum-of-multiples) got me back to _advanced for loops with guards_ and gave me a spoiler on collections (using Sets) & _foreach_.  

The problem :
``` text
Given a number, find the sum of all the unique multiples of particular numbers up to but not
including that number.
 ```

My solution:

```scala
object SumOfMultiples {
    def sum(factors: Set[Int], limit: Int): Int = {

      // Create a collection to hold the multiples
      val multiples = collection.mutable.Set[Int]()

      //for each factor, look for the multiples and add them to the Set
      factors.foreach { factor =>

        for (i <-1 to limit-1 if ( i%factor == 0)){
            { multiples += i}
        }
      }

      println(multiples)

      // Sum the values of the elements in the collection
      multiples.foldLeft(0)((total, current) => total + current)

    }
}
```

Tomorrow I will dedicate my day to Exercism and take some learnings out of the solution in the community. :)

[🎶 of the day](https://www.youtube.com/watch?v=CD-E-LDc384)
