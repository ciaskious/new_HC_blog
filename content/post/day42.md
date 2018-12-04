---
title: "Day42: Akka http by example"
date: 2018-12-03T12:36:08+01:00
tags: ["akka-http", "Scala", "sbt", "docker"]
draft: false
---

It was about time to try out akka http and dockerize a small example app. In this post I will explain step by step how to write a "Hello (wait for it...) World" and put in a Docker container using the [SBT Native Packager](https://sbt-native-packager.readthedocs.io/en/latest/index.html). The main example can be found in the [akka docs](https://doc.akka.io/docs/akka-http/current/routing-dsl/index.html)

First things first, Akka HTTP is not a framework; it is a more general solution for HTTP services, built on _akka stream_ and _akka actor_. In the future, I want to try out web-frameworks based on Akka, like Play or Spray, but for now the point is to understand the actor system and routes.  The reason I used it today: I just needed to integrate an HTTP layer in my project. In addition, Akka HTTP offers abstraction by giving you the freedom to use different level APIs for the same task.

To get started with his project, we have to add the dependencies to our **build.sbt** file:  

```Scala
name := "akka-http-example"

version := "0.1"

scalaVersion := "2.12.7"

libraryDependencies ++= Seq(
  "com.typesafe.akka" %% "akka-actor" % "2.5.13",
  "com.typesafe.akka" %% "akka-stream" % "2.5.13",
  "com.typesafe.akka" %% "akka-http" % "10.1.3",
)
```  

## _akka-actor_   

![an event-driven actor system](/images/actors.jpg)  

Actors are entities that make concurrent computations and affect each other only through messages. Every actor has an isolated, private state and it can:  

* Make decisions
* Create more Actors  
* Send messages
* Decide on how to behave to the next message received  


## _akka-streams_  

Streaming data is the process of feeding data sequentially in micro-batches. Actors can also handle streams, in the form of message-series, in order to send and receive information.  

## _The Hello_  

As we have the core concept, lets try to implement it by creating first an actor system that will take care of the concurrent requests.  
`implicit val system = ActorSystem("Example")`  

We then make use of the akka streams and specify the flow materializer. The flow is a set of stream processing steps that has one open input and one open output. The _ActorMaterializer_ here is picked up implicitly and decides how the flows get processed.  

`implicit val materializer = ActorMaterializer()`   

We then need an execution context in order execute the future flatMap/onComplete at the end of our app. Every _ActorSystem_ has a dispatcher, here we use the default one.

`implicit val executionContext = system.dispatcher`  

It is time to define our route. Akka, in the higher Level API, uses a routing DSL to describe the routes. It turns every route into _Future[RouteResult]_, a type that defines how every type of request should be handled.

```
val route =
      path("hello") {
        get {
          complete("Hello HolidayCheck!")

        }
      }
```  
In this case for our request (GET) to /hello, we would receive a "Hello HolidayCheck!" response.

To wrap it up, we have to bind this route to a server with an interface and a port.
```
val bindingFuture = Http().bindAndHandle(route, "localhost", 8080)
   println(s"Server online at http://localhost:8080/\nPress RETURN to stop...")
   StdIn.readLine() // let it run until user presses return
   bindingFuture
     .flatMap(_.unbind()) // trigger unbinding from the port
     .onComplete(_ => system.terminate()) // and shutdown when done
```  

Now that I am sure that my post is perfectly written and no problems have occurred as you are trying this yourself, I will proceed to a very nice tool - the SBT Native Packager. Just by adding this plugin to your project/plugins.sbt file:
`addSbtPlugin("com.typesafe.sbt" % "sbt-native-packager" % "1.3.15")  
`   
and enabling it in the built.sbt  
```
enablePlugins(JavaAppPackaging)
mainClass in Compile := Some("Server")

enablePlugins(DockerPlugin)
packageName in Docker := "akkahttp"
dockerBaseImage := "openjdk"
dockerExposedPorts := Seq(8080)
```  
The **JavaAppPackaging** is an archetype that will use the mainClass setting of sbt (automatically discovers your main class) to generate bat and bin scripts for the project.  
You can first run _sbt stage_ and have it run locally without being packaged. You will find it at _./target/universal/stage/bin/akka-http-example_.  

  Then, to create the docker image, we first define parameters that we would normally include in our Dockerfile. For this Scala project, we use the _openjdk_ base image and after creating our container, it will be accessed via port 8080. This is the port that the "outside world" needs in order to see our container and not the one we defined in our app. On top of that, now we have to go back to the app and change the interface from "localhost:8080" to "0.0.0.0:8080". As docker is running on a Virtual Machine, we need to bind to this wildcard ip address in order to match any possible ip on the host.  
  ```
  val bindingFuture = Http().bindAndHandle(route, "0.0.0.0", 8080)  
  println(s"Server online at http://0.0.0.0:8080/\nPress RETURN to stop...")
  ```

 We are almost at the finish line. All left to do is type in the sbt  
 `docker:stage`  
 `docker:publishLocal`  
 You will now be able to see your image if you do `$ docker images`. Then, you can run a container with
 `$ docker run <name of your image>`.   
 Now you can see your response your response if you `$ curl http://0.0.0.0:8080/hello`.  
  


![winner](https://media.giphy.com/media/l41JTmjI1p0FkSBuU/giphy.gif)  
[Source: giphy.com](https://gph.is/2u8YVJl)

And this was my first attempt to write a fully hands-on post on this blog. More will follow this week! <3   

[Song of the day] (https://www.youtube.com/watch?v=f79avl6ZMC8)
