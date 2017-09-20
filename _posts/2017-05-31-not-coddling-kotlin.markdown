---
layout: post
title:  "Lets not coddle you, Kotlin"
date:   2017-05-31 09:44:00 -0500
categories: cliffnotes kotlin
---


### The Programming Language: Kotlin ###

**History:**
  - Announced as something JetBrains was doing in 2011
  - Released for support on February 2016
  - Goal to support a set of features desired by JetBrains and not available in any language except Scala.
    (Scala compiled too slowly)

**Concepts:**

  - TBD

  
**Pros:** 

  - Concise:  _write less code_
    - case or if/else statements are so much sweeter!
    - can inline functions
    - infers types (removing need to specify)
    - you can use "x" variable directly where there's a getter/setter for x in a class.
    - and otherwise eliminates syntactic sugar.

  - Null Safety
    - @compile time safety-- type indication and method protection
    - safety (e.g. Elvis) operators (do X unless this is null in which case skip)

  - Extensions (even to java's normally protected classes like String)
  

**Cons:**

  - As of 2016 September (Review by DripStat-- Kotlin the Good Bad & Ugly), they rate the language as top-notch, but the IDE was so buggy as to not be usable.  That key issue is closed as obsolete, but the warning here is that the IDE & plugin is not production stable (as of Sep 2016).

  - Has some minor limitations over pure Java 8.

  - Hidden complexity can cost
    - you may not understand/think about what it's doing behind the scenes.
    - Can create duplicate anonymous classes. (e.g. makes it easy to do, you may forget that there's actually java classes/lambdas behind them.)
    - You can work around it, but you need to understand it to know when to _inline_ vs not...
        (See ~30:00 [VIDEO Android Development with Kotlin])

**Recommendations:**
    - use inline functions for extensions
    
### Sources ###
  - [Kotlin Org]
  - [Wikipedia Kotlin]
  - [Kotlin the good bad ugly]
  - [Some favorite features]
  - [VIDEO Android Development with Kotlin]


[Kotlin Org]: https://kotlinlang.org/
[Wikipedia Kotlin]: https://en.wikipedia.org/wiki/Kotlin_(programming_language)
[Kotlin the good bad ugly]: http://blog.dripstat.com/kotlin-in-production-the-good-the-bad-and-the-ugly-2/
[Some favorite features]: https://m.signalvnoise.com/some-of-my-favorite-kotlin-features-that-we-use-a-lot-in-basecamp-5ac9d6cea95
[VIDEO Android Development with Kotlin]: https://www.youtube.com/watch?v=A2LukgT2mKc



