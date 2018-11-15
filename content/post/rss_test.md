---
title: "Day17 & 18: RSS and baby steps"
date: 2018-10-25
tags: ["apprenticeship", "scala"]
draft: false
---

### RSS Y U NO WORK?

There was an idea. There were supporters.  
There was passion. There was disappointment.  
Yesterday was a sad day...It was the day that slack let me down ( a little bit). The idea was to put an rss feed in our blogs. As we are 5 apprentices already in HC, the blogs are getting too many to follow. The first to try it, was me and Deirdre ([more on this tragedy](https://dbringas.netlify.com/posts/day38/)). We joined our forced and quickly put the feed link on the site. But soon, the problems started... Long story short, we wanted to push notification on slack. There is an integration already and all you have to do is subscribe to a feed, so yeah easy peasy, right? Well, until we tested the feed with a chrome extension, we thought we had a problem. But as we both got notified about our new test post, mmmm... SLACK APP Y U NO WORK?  

![y u no work meme](/images/y-u-no.jpg)

So, we left this aside as it made no sense - after some point we were just waisting our time. But the rest of the team's joining us tomorrow and we might come up with a better idea :D

### Exercism

As I had to leave earlier yesterday, it would make no sense to write a post only complaining about the rss situation. I completed 2 more exercises and although they were easy, I made the things complicated again and learned by failing. I have talked about this before: ``` my tendency to overthink 👎 ``` I promised as an apprentice to take baby steps and keep things simple. I knew that every adult step in these exercises would hide more & more gaps in Scala that I haven't covered yet, but this excites me and keeps me motivated.  
The more I implement, the faster I learn. Although my solutions are not checked or corrected (yet), I still have the ability to get better by seeing the solutions the community has given. I see that I have the same approach with many devs, but some more experienced give advanced solutions that I still cannot even dream of. It is gives me some confidence to see that I am not stupid (even if I am, at least I am not the only one 😂) when I write simple code.  
The key is a step at a time. It is so awesome that they give you the test to start with, I am slowly getting used to it.

```scala
val x= "it" match  {  
    case "baby steps" => "Irrelevant, but it was about time"  
    case "TDD" => "Exercism helps but you have missed all katas this week"
    case _ => "Ain't nobody got time fo dat"
  }  
```

Yes, I jumped into pattern matching for an exercise ;)  

```scala
object Day16{
  def main(args: Array[String]) {
    val AnastasiaReallyMeans = Map("I am hungry" ->"I could eat you alive!", "coffee" -> "COFFEE NOOWWW")
   }

  def answer(x: Option[String]) = x match {
    case Some(s) => s
    case None => "What do you mean Anastasia?"
  }
}
```

And scala Options, as well!! <3


[🎶 of the day](https://www.youtube.com/watch?v=Vlo2I-wF6CY)
