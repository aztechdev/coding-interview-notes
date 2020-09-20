# Data Structures

What is a data structure? My favourite website Wikipedia provides a good definition:

> ...a **data structure** is a data organization, management, and storage format
> that enables efficient access and modification. More precisely, a data
> structure is a collection of data values, the relationships among them, and
> the functions or operations that can be applied to the data.

## Hash Tables / Hash Maps

> Type: Unordered associative array ([Hash table - Wikipedia](https://en.wikipedia.org/wiki/Hash_table))

Search | Insert | Delete | Space
--- | --- | --- | ---
`O(n)` | `O(n)` | `O(n)` | `O(n)`

A hash table is a structure that can map keys to values. A hash map uses a hash
function to compute an index into an array of buckets or slots, from which the
desired value can be found.

Advantages | Disadvantages
--- | ---
Speed when the number of entries is large | Not effective when the number of entries is very small

## Linked Lists

> Type: List ([Linked list - Wikipedia](https://en.wikipedia.org/wiki/Linked_list))

A **linked list** is a linear collection of data elements whose order is not
given by their physical placement in memory. Instead, each element points to the
next. It is a data structure consisting of a collection of nodes which together
represent a sequence. In its most basic form, each node contains: data, and a
reference (in other words, a link) to the next node in the sequence. This
structure allows for efficient insertion or removal of elements from any
position in the sequence during iteration.

- Singly-linked list: linked list in which each node points to the next node and
the last node points to null
- Doubly-linked list: linked list in which each node has two pointers, p and n,
such that p points to the previous node and n points to the next node; the last
node's n pointer points to null
- Circular-linked list: linked list in which each node points to the next node and the last node points back to the first node

Access | Search | Insert | Delete | Space
--- | --- | --- | --- | ---
`O(n)` | `O(n)` | `O(1)` | `O(1)` | `O(n)`

<!-- - Trees, Tries, & Graphs
- Stacks & Queues
- Heaps
- Vectors / ArrayLists / Dynamic arrays -->

## Useful Links

[List of data structures - Wikipedia](https://en.wikipedia.org/wiki/List_of_data_structures)

[Search data structure - Wikipedia](https://en.wikipedia.org/wiki/Search_data_structure)

[MIT 6.046J Design and Analysis of Algorithms, Spring 2015](https://youtu.be/2P-yW7LQr08)

[MIT 6.006 Introduction to Algorithms, Fall 2011](https://www.youtube.com/playlist?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

[MIT 6.046J / 18.410J Introduction to Algorithms (SMA 5503)](https://www.youtube.com/playlist?list=PL8B24C31197EC371C)