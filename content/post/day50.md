---
title: "Day50: Scala Adventures"
date: 2018-12-13T15:54:44+01:00
tags: ["akka-streams"]
draft: false
---
It has been more than a week that I haven't written a single word in this blog. Too bad or just bad, I have no idea. On Monday, the business phase of my apprenticeship started and I love it. For a soft transition to this phase, I have joined a tech product team. But in the future I will try to follow non-tech teams in order to get a grasp of all the different sides of HolidayCheck and what each one of them does for the Urlauber. And as I haven't posted since last week, the amount of triggers for new knowledge that I have collected is MASSIVE! I think I have an infinite source of blog-topics for the next 4 weeks ;)  

So as the title implies, I have been mostly working with Scala and this made me extremely happy. Breaking free from the book and being stupid in front of the IDE can be so frustrating but learning in a supportive environment with experienced colleagues can quickly put you back to the path of sanity. And this gives me valuable learnings both about the tools I am using and of course, my beloved Scala.  

### Akka knocked again on my door :)
 My [last post](https://ciatastrophe.netlify.com/2018/12/03/day42/) was about akka-http. Today it is about `akka-streams`.  

#### To stream or not to stream?

Handling data as streams of events has become the standard for most data-driven organizations, mostly because it is much faster to do real times computation with "live" data and give immediate response. We build reactive systems, which means that we use a **message-driven** architecture in order to create **responsive** applications that are **resilient** and **elastic** (scalable). These are not my words, it is the `reactive manifesto` and there is already an [amazing article on reactive programming](https://blog.redelastic.com/what-is-reactive-programming-bc9fa7f4a7fc) for you to read more details. I will stay on the *message-driven* part though.

### Message-driven?  

This is where concurrency and actors come into the game. To make it more complicated, Akka-streams are an Actor-based implementation of Reactive Streams in the Scala World. Reactive Streams refer to the way streams should be processed on the JVM, so that they are  

* non-blocking: operations do not block each other from executing, even if they are not finished.
* asynchronous: operations do not have to be executed sequentially.   

Message-driven applications are triggered by events. I will copy paste from the amazing article above  

> An event-driven system is based on events which are monitored by zero or more observers...   
...The big difference between event-driven and imperative style is that the caller does not block and hold onto a thread while   waiting for a response. The event-loop itself may be single threaded, but concurrency is still achieved while invoked routines go about their business (and potentially block on IO themselves) while allowing the (sometimes single) threaded event-loop to process incoming requests. Instead of blocking on a request unless completely processed, the caller’s identity is passed along with the body of the request message so that — if the invoked routine chooses to do so — the caller can be called back with a response.  

A problem though --> the so-called callback hell. But still, not the case in this post. [For more...](http://callbackhell.com/)  
On the other hand, we have actor-based concurrency  

> Actor-based concurrency is an extension of the message-passing architecture, where messages are directed to a recipient, which happens to be an actor.  

So in this case, we have events that are treated like messages by the actors.  
Message driven could be event-driven, actor-based or even both!  

### How to stream - the basics abstractions  

Super basics - all I know for now.  

![source and sink](/images/source-sink.jpg) ![flow](/images/flow.jpg)  
Streams are pipelines that move data and consist of different stages that transform them.   
**Flow** is a stream that has an open input and an open output - the BidiFlow has 2 of each. The **Sink** is a stream which has only one open input and the **Source** only one open output accordingly.  
Usually, the puzzle goes like Source --> Flow --> Sink, although there are many ways to wire the streams.
Such a Stream would look like:  

```
Source(1 to 10).via(Flow[Int].map(_ * 10)).to(Sink.foreach(println(_)))
```

The terminology feels already huuuge! I will definitely continue reading into streams and try to write better implementations next week in order to understand more and in-depth.

[Song of the day] (https://www.youtube.com/watch?v=p3l7fgvrEKM)
