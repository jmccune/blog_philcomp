---
layout: post
title:  "Catching the message bus..."
date:   2017-03-03 13:57:00 -0500
categories: message-bus kafka
---

### Kafka ###

Kafka:

 - **Origin**
   - Started at LinkedIn to:
     + decouple producers & consumers
     + persistence for written data (allow multiple consumers)
     + optimize high throughput of messages
     + horizontal scaling as data streams grow
   - Taken Open Source in 2010
   - Since it is meant to write (messages) then based on a writer (Franz Kafka)
   - Initial Authors: Jay Kreps, Neha Narkhede, and Jun Rao
 - Never duplicate or lose a message.
 - Use groups to make sure a single message is read.


### Sources ###
  - [Kafka]


[Kafka]: https://www.safaribooksonline.com/library/view/kafka-the-definitive/9781491936153/ch01.html#idm140651335055984
