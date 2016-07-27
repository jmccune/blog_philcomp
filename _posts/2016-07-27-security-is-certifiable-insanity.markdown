---
layout: post
title:  "Security is certifiable insanity!"
date:   2016-07-27 08:00:00 -0500
categories: security
---

Security is often done over SSL  (Secure Socket Layers) which really means certificates and authorities and trust.
A good description of what this is is here [what-is-ssl]

I just want to capture the things you often need to do and how they work in Java.

Terminology:


- <span class="blue">**TRUSTSTORE**   - (USED FOR READ) </span> 
	a store of certificates that are to be trusted.
	These can be both those certificates that are generally trusted
	in the public domain, as well as those custom to a particular 
	application/domain/organization.

	These are used to establish whether clients of the service
	are who they say they are (because their certs are signed
	by trusted authorities in the truststore).


- <span class="pink">**KEYSTORE**  -(USED FOR WRITE)   </span>
	 While using an equivalent file representation as a
	truststore (for java), these contain private keys/certificate
	information used to SIGN the certificate indicating that messages
	sent by the server to other parties are authentic and issued
	by the actual server.





[what-is-ssl]: https://www.sslshopper.com/what-is-ssl.html