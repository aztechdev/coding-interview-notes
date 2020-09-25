# The Fast & Slow Pointers Pattern

This approach is sometimes referred to as the **Hare & Tortoise algorithm**,
using two pointers at different "speeds". This can be useful when dealing with
cyclic LinkedLists/arrays. The reasoning behind this is that eventually, if the
structure is cyclic, the pointers will eventually meet up. For example:

**_Given the head of a Singly LinkedList, write a function to determine if the LinkedList has a cycle in it or not._**