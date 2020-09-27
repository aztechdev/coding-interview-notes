# The Fast & Slow Pointers Pattern

This approach is sometimes referred to as the **Hare & Tortoise algorithm**,
using two pointers at different "speeds". This can be useful when dealing with
cyclic LinkedLists/arrays. The reasoning behind this is that eventually, if the
structure is cyclic, the pointers will eventually meet up. For example:

**_Given the head of a Singly LinkedList, write a function to determine if the LinkedList has a cycle in it or not._**

In each iteration, the slow pointer will move one step, and the fast pointer will
move two steps. This means that if the LinkedList doesn't have a cycle in it, the
fast pointer will reach the end of the LinkedList before the slow pointer. However,
if the LinkedList does have have cycle, if the two pointers meet we know that we
have a cycle. When the fast pointer is behind the slow pointer, it is either one
step or two steps behind the slow pointer. Therefore there are two scenarios:

1. **If the fast pointer is one step behind the slow pointer:** the fast pointer
moves two steps and the slow pointer moves one steps, meeting each other.

2. **If the fast pointer is two steps behind the slow pointer:** after each
pointer moves, the fast pointer will be one step behind the slow pointer, which
reduces to the first scenario.

```js
class Node {
  constructor(value, next = null) {
    this.value = value;
    this.next = next;
  }
}

function listHasCycle(head) {
  let slow = head;
  let fast = head;
  while (fast !== null && fast.next !== null) {
    fast = fast.next.next;
    slow = slow.next;
    if (slow === fast) {
      return true; // found the cycle
    }
  }
  return false;
}
```

Given that `n` is the number of nodes in the LinkedList, the above algorithm
should find the cycle in `O(n)`.

Another popular problem is to find the length of the cycle in the LinkedList, and
this can be found by tweaking the algorithm above. Once the fast and slow pointers
meet, we can save the slow pointer and iterate through the cycle with another
pointer until we see the slow pointer again:

```js
function getCycleLength(head) {
  let slow = head,
    fast = head;

  while (fast !== null && fast.next !== null) {
    fast = fast.next.next;
    slow = slow.next;
    if (slow === fast) { // found the cycle
      return calculateCycleLength(slow);
    }
  }
  return 0;
}


function calculateCycleLength(slow) {
  let current = slow,
    cycle_length = 0;
  while (true) {
    current = current.next;
    cycle_length += 1;
    if (current === slow) {
      break;
    }
  }
  return cycle_length;
}
```
