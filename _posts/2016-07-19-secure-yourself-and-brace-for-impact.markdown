---
layout: post
title:  "Secure Yourself, and brace for impact!"
date:   2016-07-18 17:00:00 -0500
categories: security
---

### Securing your future...

These days with social engineering, scams, identity theft, frauds, etc.
it's not surprising that security is a critical consideration in more
and more of our every day life.  This is true of both your own work place
and more challengingly any organization you do business with.

Ultimately, security is about knowing that sensitive information is kept safe

  - not acquired by unauthorized parties
  - not alterable or destroyable by unauthorized parties
  - is accessible and usable only by the permitted parties
  - can be exchanged (without loss or compromise) between permitted parties

Physical safes and/or institutions like banks perform this function for
physical assets.  Things kept in safes/lock-boxes are guarded against by the
institution's security measures as well as the physical locking mechanism.
The security measures ensure that only the authorized party (the authorized
key holder) is able to open/unlock the safe/lock-box.   Thusly the contents in the safe
are not normally subject to alteration, destruction or for copying/capture.
And they can only be exchanged by removing them from the box and using secure means of
exchange (secure couriers or directly handing the contents to someone else.)
One nice aspect of most physical things is that they don't copy easily.

In the computer world, we don't rely on physical measures.  Digital information
is too easily copied, alterable, destroyable.  Math solves this problem by
providing encryption which guards against the information being altered
or usable by unauthorized parties.

Encryption & Decryption are a process of encoding & decoding a message that
provide safety such that:

- if it's altered, the message will not decode properly (indicating a potential compromise)
- if it's copied -- the message remains difficult/almost-impossible to decode and exploit
		without the key.  Therefore the actual contents/information are not successfully
		acquired by unauthorized parties -- even if the container (encrypted message) is.
- with the proper key the message can be decoded and
	is accessible and usable by the permitted parties

Encryption works between two parties and is a great solution.

The easiest way to understand security is to think of one message being exchanged
between two parties.   In reality, this is overly simplified.

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
are multiple ways of doing so.  Which brings us to the means of
providing security.

_Please note that security protocols are often
attacked and sometimes successfully exploited.  The design and
validation of security protocols is its own field of study & research
and should not be  undertaken except by security professionals._


### SAML

SECURITY ASSERTION MARKUP LANGUAGE

SAML is a means of performing authorization & authentication between
parties and is most commonly used for Single Sign On (SSO) in the
browser.  As suggested by its name, it is an XML based message exchange
protocol that allows the secure exchange of information known as assertions.

The two parties in this protocol are identified as the:

 - _the Identity Provider_ - think logging on with your Facebook/Google credentials
 - _the Service Provider_ - the service you are trying to use after logging in

The ServiceProvider will generally redirect the user (via the Browser)
to the IdentityProvider so that the IdentityProvider may log them in
(or redirect them back immediately if they are already logged in).  Once
authorized the Identity Provider redirects back to the ServiceProvider with
information (formally called assertions) about the identity of the user.
These assertions provide information about the user
(e.g. e-mail address, username, organization,etc.)
and are agreed to in the exchange of metadata by
the IdentityProvider and the ServiceProvider at startup.

The IdentityProvider may have other controls that are used to
enable the exchange of information and/or even to authenticate
with given services/ServiceProviders.

The security of this protocol is protected by the use of
encryption via the signing of the messages exchanged, and the
use of pre-arranged/registered endpoints protected via SSL and
DNS registration (e.g. they only communicate via trusted domain
names that are verified by certificates and certificate chains).



### OAuth2

Based on:  https://aaronparecki.com/2012/07/29/2/oauth2-simplified

Terms:

 - Client - any application/service operating on behalf of the "user"
			 it needs permission
 - Resource Server - the server using/accessing the client's information.
 - Resource Owner -  The "user"


TO BE CONTINUED...

### Sources ###
  - [SAML]


[SAML]: https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language


