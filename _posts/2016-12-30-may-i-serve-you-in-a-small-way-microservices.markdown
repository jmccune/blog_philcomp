---
layout: post
title:  "May I serve you in a small way: Microservices"
date:   2016-12-30 13:45:00 -0500
categories: microservices
---

Microservices are the modern way of making things work, for handling scale for things that are "too big" for a single computer to handle.  We use microservices all the time if we use the internet.  

Microservices are for:

  * Big Systems		(Many services can acheive more than any single computer: think hadoop)
  * Replacement  		(allowing for piece-meal upgrades)
  * Manageable Scope  (Two Pizza Teams)
  * Separation of Concerns

Good Properties of Micro-services:

  * Stateless  		
  * Redundancy
	  * NodeLoss doesn't impact the system.
	  * Remove Single Points of Failure/Cascading failures	
  * Pass Chaos tests  (verify node failures don't take the system down) 
  * Multiple versions can run at the same time
  	  * The API is the contract

Observations:
  * Mature companies spend 25% of their time on the internal infrastructure
  

### Sources ###
  - [Microservice Architecture]
  - [Mastering Chaos]
  - [Reinvent Serverless Architecture]

[Microservice Architecture]: http://shop.oreilly.com/product/0636920050308.do?sortby=publicationDate
[Mastering Chaos]: https://www.infoq.com/presentations/netflix-chaos-microservices
[Reinvent Serverless Architecture]: https://www.youtube.com/watch?v=OI_V6OZZkZM