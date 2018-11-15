---
title: "Day28: Spicing it up"
date: 2018-11-09
tags: ["Scala", "currying"]
draft: false
---

Days go by like seconds... I owe my blog 3 posts already - I created the drafts and I am still not able to go back to them, proofread them and make them descent for posting...  

![batman slap](/images/batman_slap.jpg)  

There was a learning this week... ``It is nice to mix different stuff to learn together BUT NOT IN ONE DAY! ``This is the major reason I didn't finish the previous posts - I ended up so confused at the end of the day and thought I would make it better the next day. Weeeeeell, no!  

I am not gonna make a "finish by then-or-that-time your post" rule, I am just gonna make sure that everyday I am able to word my learning, without thinking of how people would judge it. Just kidding, of course I care! During the first days of the apprenticeship, I thought it was just me and my baby blog #NOT So, of course I care if people like it/ find it useful /enjoy it /have fun with it... To be honest a greek blog is a secret dream that I have always had - the only thing (or excuse) that stops me is time. But enough with the Friday confessions, let's spice this day up with some curry-ing (Ha-Ha).

### Currying

![](https://media.giphy.com/media/65GcvGilD0Xw4/giphy.gif)  

This gif would be enough if this were just a tweet, but as this is not the case let's go:

``Why currying?`` It was my first question, but the answer's not that exciting - it is named after Haskell Brooks Curry. Yes, the Haskell language, where a lot of currying is happening, is named after him as well.  

`` How come you learned today currying? `` Today I focused on FP concepts. I went back to Ordesky's course, speed it up and it FINALLY seemed like a normal course ( THANK YOU SEBASTIAN! ). It was left at the 2nd chapter and "High Order Functions". Currying was only a 14min video, so who could have imagined that I would devote a whole post on this little [b\wtch].  

Long story short about this concept:  

`` Any function that takes multiple arguments, can live its functional life also as a function with a single argument``  
I always doubt that maths can help me visualize and understand anything but [Wikipedia](https://en.wikipedia.org/wiki/Currying) proved me wrong.  

``Given a function``

``f:(X x Y) -> Z  , where X x Y the Cartesian product of X and Y``
``**currying** constructs a new function``

``h: X -> (Y -> Z). ``  


----------  This is art! -------------------  
|   That is, h takes an argument from X and returns a function that maps Y to Z.  
|   It is defined by  
|  
|     h(x)(y)=f(x,y)
|
|   for x from X and y from Y. We then also write  
|  
|         curry(f)=h  
---------- --------- so prettyyyyy  --------- ------------------  
For example:

```
def product(a: Int, b: Int): Int = a*b

def curry(f: (Int, Int) => Int) = (a: Int)=> (b:Int) =>f(a,b)

val curriedProduct = curry(product)

curriedProduct(2)(3)
```

Voilà!

It is simple example, but it was enough to help me get started. Then I finally understood in the end the course, the book and all the google results I found. Sometimes googling "simple" is just not simple enough...  

Currying is cool but the weekend's much cooler, so  

bis Monntag :)  




[Song of the day] (https://www.youtube.com/watch?v=RB-RcX5DS5A)
