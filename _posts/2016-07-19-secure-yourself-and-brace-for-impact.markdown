---
layout: post
title:  "Secure Yourself, and brace for impact!"
date:   2016-07-18 17:00:00 -0500
categories: security
---

### Securing your future...
_is about securing your application:
today we're going to talk about securing apps..._


### Overview

These days with social engineering, scams, identity theft, frauds, etc.
it's not surprising that security is an important topic that is really
important toward securing your future.

Ultimately, security is about knowing that information is kept safe

  - not acquired by unauthorized parties
  - not alterable or destroyable by unauthorized parties
  - is accessible and usable by the permitted parties
  - can be exchanged between permitted parties

Physical safes and/or institutions like banks perform this function for
physical assets.  Things kept in safes/lock-boxes are guaraded against by the
institution's security measures as well as the physical locking mechanism.
The locking mechanism ensures that only the authorized party (the key holder)
is able to open/unlock the safe/lock-box.   Thusly the contents in the safe
are not normally subject to alteration or destroyable.   And they can only
be exchanged by removing them from the box and using secure means of 
exchange (secure couriers or directly handing the contents to someone else.)
One nice aspect of physical things is that they don't usually copy easily.

In the computer world, we don't rely on physical measures.  Digital information
is too easily copied, alterable, destroyable.  Math solves this problem by
providing encryption which guards against the information being altered
or usable by unauthorized parties. 

Encryption & Decryption are a process of encoding & decoding a message that
provide safety such that:

- if it's altered, the message will not decode properly (indicating a potential compromise)
- if it's copied -- the message remains difficult/almost-impossible to decode and exploit
		without the key.  Therefore the actual contents/information are not successfully 
		acquired by unauthorized parties -- even if the safe (encrypted message) is.
- with the proper key the message can be decoded and 
	is accessible and usable by the permitted parties

Encryption works between two parties and is a great solution.

However, so often these days it's more than just point-to-point communications..

### Multi-Client Security

In the service economy in which much of the US lives, it's not just about
point to point communication.   It's about services like (PayPal) that step in to help
complete a transaction, or Google or Facebook doing your sign-on and returning you
to your site for you to post your comment...   

So drawing on the above, we wish to say that a given message is securely transmitted when:

-  the intended parties and _only_ the intended parties receive the _actual_ message.
-  only trusted/authorized intermediaries handle the message in transit
-  the message is delivered unaltered (nothing changed in transit).
-  it is known that the message was not lost in transmission.

To allow agents to act on our behalf we must add some other notes:
-  certain authorized parties receive a message and may 
	request other actions/transactions on the client's behalf.
-  care must be taken to ensure the security of such secondary
	actions/transaction.

Note:  If the latter sounds a little vauge-- it's because there
are multiple ways of doing so.  Which brings us to...



### OAuth2 

Based on:  https://aaronparecki.com/2012/07/29/2/oauth2-simplified

Terms:

 - Client - any application/service operating on behalf of the "user"
			 it needs permission
 - Resource Server - the server using/accessing the client's information.
 - Resource Owner -  The "user"


TO BE CONTINUED...
