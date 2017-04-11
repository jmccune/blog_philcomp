---
layout: post
title:  "Developing applications RESTfully"
date:   2017-04-11 09:44:00 -0500
categories: restful philosophy
---

### Designing RESTful APIs isn't always so restful for the soul... ###

As I've started a new endeavor/project-- one of the things that we've been doing is working on the design of the RESTFUL api.
I've been learning about REST and best practices, and realized that there is alot that is not settled, despite other
coworkers statements that this is how you do things in REST. There are some issues/problems that are not really solved
(e.g. where solved means _agreed upon by the community_ .)

The following articles illustrates the point that there isn't always agreement...

  * [10 best practices for better restful api]
  * [best practices for a pragmatic rest api]

They are reasonable, is supported in some of its points by many other articles/people opining similar or the same (nouns not verbs, use http status codes)
and illustrates some consensus.   However, it's not necessarily the full picture as the articles somewhat recognize (or ignore).


For example #1, consider *api versioning* where there is this: [your api versioning is wrong]  which illustrates the debate
on versioning (and that there is no agreed upon _right way_).

Or alternately you have articles like this (on security & authentication):

  * [my take on restful authentication]
  * [secure your rest api the right way]

Furthermore, when trying to figure out how to document a restful api ( youtube video found for [restdocs vs swagger] )
I was introduced more formally to the maturity model of rest ([richardsons rest maturity model])
and again to [HATEOAS].

The speaker states that in terms being fully compliant, you're not really RESTful unless you're doing HATEOAS (or level 3
of the maturity model).  That's agreed to somewhat by Fowler and others, because Roy Fielding who invented the term RESTful
to describe these types of APIs, suggested that you're not really RESTful unless you are using the application in that manner.

_That was quite a surprise to me-- I've been doing what I considered "Restful" APIs for years without implementing a HATEOAS api._


### Sources ###
  - [best practices for a pragmatic rest api]
  - [10 best practices for better restful api]
  - [your api versioning is wrong]
  - [my take on restful authentication]
  - [secure your rest api the right way]
  - [richardsons rest maturity model]
  - [HATEOAS]

[best practices for a pragmatic rest api]: http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api
[HATEOAS]:https://en.wikipedia.org/wiki/HATEOAS
[richardsons rest maturity model]: https://martinfowler.com/articles/richardsonMaturityModel.html
[restdocs vs swagger]: https://www.youtube.com/watch?v=k5ncCJBarRI
[secure your rest api the right way]: https://stormpath.com/blog/secure-your-rest-api-right-way
[10 best practices for better restful api]: https://blog.mwaysolutions.com/2014/06/05/10-best-practices-for-better-restful-api/
[your api versioning is wrong]: https://www.troyhunt.com/your-api-versioning-is-wrong-which-is/
[my take on restful authentication]:https://facundoolano.wordpress.com/2013/12/23/my-take-on-restful-authentication/