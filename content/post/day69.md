---
title: "Day69: SQL "
date: 2019-01-22T12:36:43+01:00
tags: ["databases"]
draft: false
---
As mentioned in a previous blog post, I discovered how little (practical) knowledge I have on databases. Today, I will use this blog post to document my progress while learning more about SQL databases, using MySQL for a specific use case. The point is to validate the differences between NoSQL and SQL databases by tomorrow afternoon (hopefully), while using them both on the same scenario - searching for the ideal holidays destination. I will run them in containers, so maybe other side - challenges might come up.
In the little time that was left after meetings and some theory, here are my baby steps.  

### The set-up  

1) Create the dockerfile  

  Nothing more than a dockerfile with the mysql base image.  
  ```
FROM mysql:8.0.14
  ```
  I kept it simple, but it was so stupid of me that I didn't add a volume in my dockerfile, so that I can dump my database to the host at the end of the day. The moment my container stops it is gone, which I didn't take into consideration at the beginning.

2) Build your image and run your container  
```
docker build -t mysql-image -f mysql.Dockerfile .  

docker run --rm -it \
	--name play-mysql \
	-e MYSQL_ALLOW_EMPTY_PASSWORD='yes' \  "just for now I am asking for root password to get this running"
	mysql-image
```  

Now that mysql server is up, we can get in the container
```
docker exec -it play-mysql /bin/bash
```
and just run mysql.

### The MySQL part

MySQL is a relational database. Data is distributed across tables and use schemas. Having a scenario of a simple search based on your Destination, Travel type and Airport, and with some help from my fellow Apprentice, I finally got unstuck from my complicated thoughts of giant queries and crazy relations.  

So, after creating the tables above plus with hotels (I will not copy paste the sql here today, instead I will wrap it up tomorrow when it makes some sense), I have to create them again, as accidentally stoping the container everything was gone along with my patience. At least I managed to write 2 simple queries.  
So in all my honesty, first day on designing a database was frustrating and creating it into a container was devastating. Posting about it gives no value to humanity, but at least I might be laughing at myself in the future for this.  

[Song of the day](https://www.youtube.com/watch?v=04F4xlWSFh0)
