---
layout: post
title: HashMap in Java!
---

# HashMap in Java

HashMap is a very widely used data structure in java to map keys to values. It can provide O(1) access and insertion time. However, HashMap maintains no particular order of the key-values inserted. Here is how it briefly works. A HashMap internally uses an array to provide O(1) access time. Each location in this array provides a bucket. A bucket can store multiple (key,value) pairs. To describe briefly, here is what happens when a (key,value) pair is inserted. 

1. hashCode of key object is computed using key.hashCode()
2. The hashCode value from step 1) is then mapped to one of buckets in the array.
3. Now, the key may or may not exist in the chosen bucket. 
4. If the bucket is empty, the (key,value) is simply inserted. If bucket is not empty, the key to be inserted is compared with existing keys using equals method. In case of a match, the new value is overwritten at the key. If there is no match with any of the keys in the bucket, its simply inserted along with the value which is same as step 3).


Here are some things to keep in mind while using HashMaps.

### equals-hashCode Contract
- If 2 objects are equal (== or equal method returns true), their hashcode must be same
- If 2 objects have same hashcode, that does not mean they are always equal

If a custom object is being used as a key for a HashMap, its always important to implement equals and hashCode method that satisfies the above contract.

### immutable key

The field(s) of the key object that are used in hashCode and equals method should be immutable. 

### key implements Comparable

Its a good idea to for the key Class to implement java.lang.Comparable interface. Here is why. A HashMap bucket can contain multiple (key,value) pairs. Using the Comparable interface, the process of finding a key in list of (key,value) pairs is much faster.

### Synchronization

HashMap is not synchronized data structure. So, its not advised to use them when there are multiple threads inserting/accessing (key,value) pairs. Use a HashTable or ConccurentHashMap instead.






###Links
[https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)
