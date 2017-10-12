---
layout: post
title:  "How to get some cache..."
date:   2017-04-11 09:44:00 -0500
categories: cliffnotes redis memcache cache
---

### Caching ###

This is just a summary of the differences between memcached and redis:

  1. Memcached is older:  Written by Brad Fitzpatrick in 2003 for the LiveJournal website in PERL
     (and then translated to other languages.)
  2. Redis is newer: Salvatore Sanfilippo in 2009, prototyped in ?, then productionized in C
  3. Both are extremely popular-- effective & simple.
  4. **MemCached**
       - LRU caching
       - Subject to memory fragmentation
       - consumes less memory locally
       - stores strings
       - Key size limit: 250 bytes
  5. **Redis**
       + 6 different eviction policies (not just LRU)
       + Lazy vs Active eviction
       + Data structures (not just strings)
           + storing fields & values, objects
           + lists, sets, sets, bitmaps, geo-indexes, etc.
       + Key size limit: 512 MB
       + Data manipulation (via Redis not server-side)
       + Availability & Data Replication
       + Metrics
       + Introspection
       + Because of scale-- can speed up Spark and other BigData jobs








### Sources ###
  - [Why Redis Beats Memcached]
  - [Redis in Action]

[Why Redis Beats Memcached]: http://www.infoworld.com/article/3063161/application-development/why-redis-beats-memcached-for-caching.html
[Redis in Action]: https://www.manning.com/books/redis-in-action
