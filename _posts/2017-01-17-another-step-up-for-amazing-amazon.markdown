---
layout: post
title:  "Another step up for amazing amazon"
date:   2017-01-17 08:00:00 -0500
categories: aws lambda step
---

# Step Functions Notes

Uses lambda functions to accomplish-- many different ones interconnected, that follow different states.


# Approaches (not necessarily good ones)
  * Chaining (synchronously) 
  * Database Coordination
  * Queues 

The problems with the above-- you spend time writing scaffolding, problems scaling, managing errors, etc.
Amazon wanted to simplify things for you, so they've provided the framework to do so...

# AWS State Machines (Motivation)
  * Scales
  * Doesn't lose state
  * Deals with errors/timeouts
  * Easy to build & operate
  * Auditable

This is not theory-- Amazon is running statemachines with billions of operations per week.  It's debugged & robust.

# AWS State Machines (How)
   * Cli
   * API
   * Uses JSONPath internally to select relevant elements (for input, for processing paths, etc.)
   * Best Practice:  (Single function that does one thing-- error handling outside of that step).\
   * Best Practice:  Almost all lambda functions should be wrapped with error-handling.
   * Best Practice:  Use a Lint to check before setting up your State.	
   * Can run non-lambdas (by polling HTTP to a REST endpoint).
   * Can run up to one year.

# Notes
   * You still have to worry about error-handling
   * You have to know (roughly) how much memory your functions consume

Step Functions are for:

  * Parallelization
  * State Machines
  

### Sources ###
  - [Reinvent AWS Step Functions]
  - [Reinvent Serverless Architecture]

[Reinvent AWS Step Functions]: https://www.youtube.com/watch?v=75MRve4nv8s
[Reinvent Serverless Architecture]: https://www.youtube.com/watch?v=OI_V6OZZkZM

