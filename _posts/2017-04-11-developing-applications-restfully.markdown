---
layout: post
title:  "Developing applications RESTfully"
date:   2017-04-11 09:44:00 -0500
categories: restful philosophy
---

## Designing RESTful APIs isn't always so restful for the soul... ##

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

### Design Considerations ###

General Concerns:

  - *Addressability*
  - *Safety*
  - *Idempotency* -  Produces the same effect on state, but may result in a different response.  (Example:  DELETE x,  DELETE x -- the first
      response says "DELETED", the second response might respond "NOT FOUND" or "ALREADY-DELETED")
  - *Statelessness* - The result of a previous request doesn't depend on previous requests having been made.


#### Safety / Idempotence####

Safety is in regards to the fact that the _web/networks/hardware sometimes fail and requests may be recieved
out of order, not at all, multiple times,etc._   The question is what happens when the exact same request is received
in the above situations.

  - POST - is NOT idempotent and is designed to CHANGE state (CREATE or APPEND data) every time it successfully completes.
  - GET - Get is assumed to be repeatable and NOT have any *significant* side-effects or otherwise to change-state.
  - PUT - Put is assumed to be idempotent -- if 1 call of PUT to "update/replace" a resource is received,
          the server is expected to be in the same state as if it had received any number more of  *identical*
          PUT calls.
  - DELETE - Is NOT assumed (by web-standards) to be idempotent, although a particular API may be.
            E.g an API May or may not be idempotent -- e.g. deleting  ".../resource/{id}" is idempotent
            (once the resource is deleted, it is still deleted no matter how many identitical calls are made).
            However a DELETE to a resource ".../resource/first" is NOT.
            It will delete one resource after another until none are left.

There is a caveat on GET and side-effects changing state.  For example, we expect the method that is being processed may
write to a log, increment a hit counter, etc.   But the effects are minor, indirect and more for tracking/meta-data that
is being changed. The (non-meta) RESOURCE state is not being materially changed.

HYPOTHETICAL:

What happens when you want to *get* an answer, but just "returning" the answer materially affects
the resource?  (e.g. once the answer to an exam is shown, we don't allow the user to change their
answer any more.)   What is the appropriate method to use?  GET?  or PUT?

GET is the typical verb -- the user is just fetching the answers.  But it changes resource state in
a way that is material to the resources in question (the exam), which you're not supposed to do with GET operations.

We are not PUTTING any information intentionally -- this is more a MATERIAL side-effect that impacts
the resource.

It's an interesting dilemma.

SOLUTION: (was to let the GET get the answers if they were available, which was indicated by a state change
           when the questions were answered (saying I'm done with this question for good)
           or through another endpoint that marked the exam as complete)




#### Statelessness ####

The result of a previous request doesn't depend on previous requests having been made.  The "application state" belongs with the client.
The "resource state" belongs with the server.

NonStateless Example:

  - http://xyz.com/?q="foo"
  - http://xyz.com/?q="foo"&NEXTPAGE=true
  - http://xyz.com/?q="foo"&NEXTPAGE=true

Stateless Example:

  - http://xyz.com/?q="foo"
  - http://xyz.com/?q="foo"&page=2
  - http://xyz.com/?q="foo"&page=3

Removing state eliminates failure conditions:

  - loss of connection (leading to)
  - loss of session
  - retried requests (fail & retry, but then both requests come in and you're in an unexpected state)

Benefits:

  - load balancers
  - caching works

Considerations:

  - Data Liveness  (when you do a query for the top 10 results on "foo" and save it, when you come back next week will the results
                    still be the original 10 results from a week ago, or include whatever changes/updates have occurred meanwhile)

  - Authentication - Private apps usually don't want true statelessness, you're not allowed to operate on data endpoints unless
                     the system knows who you are and you have the appropriate roles/permissions for the given operation.
                     This permission per HTTP call is often accomplished with session keys (which are stateful).  There
                     are alternatives (JWT) which includes the authentication information in a signed request meaning requests
                     can truly be stateless.   However, JWT has its own set of drawbacks and limitations and so isn't always
                     appropriate for a solution.  So we may support a cross-cutting stateful solution (this requires the
                     sharing of the session key across any load-balancing/caching solutions that are used).





### Sources ###
  - [stackoverflow]
  - [RESTful Web Services]
  - [best practices for a pragmatic rest api]
  - [10 best practices for better restful api]
  - [your api versioning is wrong]
  - [my take on restful authentication]
  - [secure your rest api the right way]
  - [richardsons rest maturity model]
  - [HATEOAS]

[stackoverflow]: https://stackoverflow.com/
[RESTful Web Services]: http://shop.oreilly.com/product/9780596529260.do
[best practices for a pragmatic rest api]: http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api
[HATEOAS]:https://en.wikipedia.org/wiki/HATEOAS
[richardsons rest maturity model]: https://martinfowler.com/articles/richardsonMaturityModel.html
[restdocs vs swagger]: https://www.youtube.com/watch?v=k5ncCJBarRI
[secure your rest api the right way]: https://stormpath.com/blog/secure-your-rest-api-right-way
[10 best practices for better restful api]: https://blog.mwaysolutions.com/2014/06/05/10-best-practices-for-better-restful-api/
[your api versioning is wrong]: https://www.troyhunt.com/your-api-versioning-is-wrong-which-is/
[my take on restful authentication]:https://facundoolano.wordpress.com/2013/12/23/my-take-on-restful-authentication/