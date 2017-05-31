---
layout: post
title:  "Development Mythconceptions"
date:   2017-02-24 15:41:00 -0500
categories: best-practices worst-practices development  
---

### Development MythConceptions ###
_thanks to Robert Aspirin (RIP) for the enjoyable series alluded to in the name..._


Over one's career it's inevitable that you, your organization and the people will make mistakes.   The best you can hope for is that they are reasonably small and easy to recover from.   Other times they are not and I've taken my lumps with some organizations who have done things poorly due to misconceptions about what's important in building software or managing people.   It's not clear what the magic success formula is (in any scientific and repeatable way).  I'm sure there are  successful group or individual's who share wisdom that "this is what you do to be successful"-- but I'm not aware of any winning formula that _always_ works.

And so it's wise to look for good principles to guide your way.   What makes that difficult, is that there are many competing myths and other ideas masquerading as good principles that get in the way.

There are many many software & computer myths (some of which have been obviously debunked)

For example:

  - "There is a world need for about 5 computers"
  - SOA/XML is the way to make enterprise data excahnge seamless and effortless...
  - Agile Practices lets us iterate, we don't need to design any more...
  - If we move our business to the _cloud_ then everything will be sunny...
  - NoSQL databases are awesome and we can do away with RDBMS databases...
  - Etc.
  - Etc.

While it's easy to make fun of the myths held mainly by managers, business men, or possibly developers fresh out of school,
even experienced developers often have their own set of beliefs (some of which qualify as false beliefs or myths).

For example:

  - Goto statements are evil
  - Interpretive languages are dead (an opinion held by some circa 1990s)
  - Bar(None) Language/Framework is so much better than the Foo(l) language others use   (many strongly opinionated developers)
  - Test Driven Development is always the way to go
  - Etc.
  - Etc.

 Some languages, methodolgies, constructs are more effective  (there are studies that show such things).  However,
 just like the latest thing (Big-Data, NoSQL, Go, Data Scientists & UX/UI designers) doesn't replace all (or even most) of what went before
 (servers, RDBMS, Fortran/C/C++/Java, Programmers) what you almost always have is a series of trade-offs, pros & cons
 and the solution depends on several factors. And several things that used to be taboo or dying have a way of being
 rediscovered, or coming back again (slightly different and better than ever).

 Figuring out those pros & cons/trade-offs in advance is difficult.   It's why certain guidelines (Martin Fowler or the Gang of Four) are cited & used so heavily-- because they do provide that guidance in advance.   However, like most things
 hind-sight tends to be much more clear than foresight.  It is easier to identify _more_ clearly with Retrospectives, Post-Mortems, etc. where things went wrong (or at least several leading contenders/contributors to what sank the ship, be that the
 Titanic or the S.S. Dingy ).

While some myths have been debunked over time others continue to persist.  I suspect it's because there is little scientific/repetable evidence about certain practices (too many variables, not enough controlled groups vs experiment groups, etc.).  Every individual/team is
unique just like all the others.  And its only recently that there is perhaps enough aggregate code repositories to do better
analysis to average out some of that uniquness.   So ignoring the scientific study (which I haven't done), what comes below is definitely subjective and a personal opinion, and definitely could be a myth-- _I'll leave it for you to decide_...

### A Myth to live by... ###

I believe a relevant statement by Tolstoy can be applied to software development...

_"Happy families are all alike; every unhappy family is unhappy in its own way."_
       -- Tolstoy

Which is to say that there are many ways to devleop software incorrectly-- and teams that deliver success repeatedly will share
all of the key and critical elements necessary to develop software correctly.  There are however countless ways to mess up
software delivery and/or the teams delivering them.

To be clear, I don't know what _all_ the right elements are.  However, I think most experienced software developers can by experience identify where problems often arise.

So here's a top N list of things that mess up projects.

# Management #

# Planning (Waterfall?) vs Reactive (Agile) #

A key principle of agile and iterating with sprints (IMO) is that you are never going to get _all_ the requirements, _all_ the UI, and _all_ the details right up front.  Agile was designed to address this by refining the product (like JPEGs resolving, or fractal image generation) so that the most expensive course corrections are done at the place of minimum cost.  It has also been noted [^Lean-Agile] that if developers had to recreate a project from scratch that _"Most developers would say that this would take only 20 to 50 percent of the time it took to write it the first time. So, what were you doing the other 50 to 80 percent of the time? You were “discovering what the customer needs” and “figuring out how to build that.”"_   I hold to this principle dearly as does much of the industry.

That means we should get rid of waterfall and _all_ its practices, right?   (Hmm... there' that throw the baby out with the bathwater idea)

!No! Being agile does not mean that you should ignore design or getting as much of what the requirements are up front.  Rich Hickey, creator of Clojure, noted that the a key problem of bugs (before design) are "problems of Misconception" [^Hammock-Driven-Development]

### Sources ###

[^Lean-Agile]: https://www.amazon.com/Lean-Agile-Software-Development-Enterprise-Objectives-ebook/dp/B002ZN2BJI/ref=sr_1_2?ie=UTF8&qid=1487972822&sr=8-2&keywords=lean+agile
[^Hammock-Driven-Development]: https://www.youtube.com/watch?v=f84n5oFoZBc   (@ ~4:30 - 5:30)
