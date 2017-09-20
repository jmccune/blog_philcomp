---
layout: post
title:  "Event Driven Opportunism (EDA)"
date:   2017-05-30 00:00:00 -0500
categories: cliffnotes eda event architecture 
---


### Event Driven Architecture ###

Concepts:

  - Decoupling
  - Events are immutable
  - Fire & Forget


Pros:
  - Avoids Concurrency & Threading issues
  - Design is more modular (testing/etc.)
  - Components can be stubbed easily


Cons:
  - Makes flow difficult to follow
  - Don't know when the flow is done. (Tricky if you want a result event if something happens)


	
### Sources ###
  - [EDA lessons learned]
  - [EDA Path to increased agility and expandability]


[EDA lessons learned]: https://www.slideshare.net/rickvanderarend/event-driven-actors-lessons-learned
[EDA Path to increased agility and expandability]: http://wso2.com/whitepapers/event-driven-architecture-the-path-to-increased-agility-and-high-expandability/

