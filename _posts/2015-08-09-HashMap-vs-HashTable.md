---
layout: post
title: HashMap vs HashTable
---

What is the difference between a HashMap and HashTable?

1. `java.util.HashMap` allows null keys and values whereas a `java.util.Hashtable` does not.
2. `HashMap` is unsynchronized and therefore much faster. However, its not suitable when there are multiple threads inserting/getting from the map. `HashTable` is synchronized and its slower because of overhead involved in maintaining locks.

`Hashtable` is old and is considered legacy. `java.lang.concurrent.ConcurrentHashMap` should be used instead. `ConcurrentHashMap` only locks certain section of HashMap during insertion. The remaining section of the map can be accessed lock free and therefore is as fast as a regular HashMap.
