Download Link: https://assignmentchef.com/product/solved-cs1332-homework-6-hashmaps
<br>
In this homework, you will implement a key-value hash map with an external chaining collision resolution strategy. A hash map maps unique keys to values and allows <em>O</em>(1) average case lookup of a value when the key is known. If adding to the table would cause the load factor (LF) to exceed (greater than, not greater than or equal to) the max load factor provided in HashMap.java, then the hash map should be resized to have a capacity of 2<em>n </em>+ 1 where <em>n </em>is the current capacity. See the javadocs for specific instructions on when to resize.

The table <strong>should not contain duplicate keys</strong>, but duplicate values are acceptable. In the event of a duplicate key, replace the existing value with the new value.

There are two constructors in HashMap.java. As per the javadocs, you should use constructor chaining to implement the no-arg constructor.

As usual, do not use magic numbers in your code. That is, use the provided constants in your code rather than hardcoding their values.

Hash Functions

You should not write your own hash functions for this assignment. Instead, use the hashCode() method (every Object has one). If this is a negative value, mod by table length first, then take the absolute value (it must be done in this order to prevent overflow in certain cases). As a reminder, you should be using the hashCode() method on <strong>only the keys </strong>since that’s what is used to look up the values.

External Chaining

Your hash map must implement an external chaining collision policy. That is, in the event of a collision, colliding entries are stored as a chain of MapEntry objects at that index. As such, if you need to search for a key, you’ll need to traverse the entire chain at the hashed index to look for it. See MapEntry.java to see what is stored and what methods are available for use; do <strong>not </strong>use Java’s LinkedList to handle the chaining functionality.

<h2>Adding Items</h2>

When adding a key/value pair to a hash map, add the pair to the front of the chain in the correct position. Also remember that keys are unique in a hash map, so you must ensure that duplicate keys are not added.

<h2>Removing Items</h2>

When removing a key/value pair from a hash map using external chaining, you can safely remove the item unlike in open addressing techniques such as linear probing where you must use a DEL marker. Removing from a chain is very similar to removing from a Singly-Linked List, treating the first table entry as the head, so refer to your notes and homework assignments from earlier in the course if you need a refresher. As usual, if the entry you are removing is the only entry at that index, you should make sure to ”null out” that spot rather than leaving it there.