# Hash Tables

> What is a Hashtable
    > technique that is used to uniquely identify a specific object from a group of similar objects.

 Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.

 > complexity

    > Since we are able to hash our key and determine the exact location where our value is stored, we can do a lookup in an O(1) time complexity. This is ideal when quick lookups are required.

  Arrays actually have fast access. If we know the index of the information we want we can access that information in O(1) time. The reason why searching for a piece of data in a collection is O(N) isn’t because the array is slow, it’s just that we have to look through all N things in the collection.

  > Structure

  * Hashing: a hash code turns a key into an integer.
 Hash codes should never have randomness to them. The same key should always produce the same hash code.

 * Creating a Hash : traditionally is created from an array.

 * Collisions: A collision occurs when more than one key hashes to the same index in an array.

> Hash Maps can have any number of buckets. If a hash map has only a few buckets it will be densely full and have many collisions. If a hash map has more buckets it will be more sparsely populated, there will be less collisions, but there may be a lot of extra empty space.

![alt](https://howtodoinjava.com/wp-content/uploads/2018/10/hashtable.gif)