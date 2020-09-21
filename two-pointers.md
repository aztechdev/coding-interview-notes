# The Two Pointers Pattern

In many problems dealing with sorted arrays (or LinkedLists) we are asked to find
a set of elements that fulfill certain constraints. For example:

**_Given an array of sorted numbers and a target sum, find a pair in the array whose sum is equal to the given target._**

A **brute force** approach would be:

1. Consider each element one by one (pointed out by the first pointer)
2. Iterate through the remaining elements (pointed out by the second pointer)
3. Find the pair with the given sum.

```js
function findSumPairs(inputArray, targetSum) {
  for (let i = 0; i < inputArray.length; i++) { // O(n)
    for (let j = i + 1; j < inputArray.length; j++) { // O(n)
      if (inputArray[i] + inputArray[j] === targetSum) {
        console.log(`${inputArray[i]} + ${inputArray[j]} is ${targetSum}`);
      }
    }
  }
}
```

The time complexity of this algorithm will be `O(n^2)` where `n` is the number
of elements in the input array. Another alternative brute force approach could
be to iterate through the array, taking one number at a time and searching for
the second number through binary search. The runtime would be `O(n log n)`. This
is slightly better but how could we make this more efficient?

Given that the array is sorted, we could start with one pointer at the beginning
and another at the end. At each step, we check if the numbers at both pointers add
up to the target sum. If they do not, we either do one of two steps:

1. If the sum of the two numbers is greater than the target sum
(_i.e._ `start + end > targetSum`), then we need a pair with a smaller sum. So,
we decrement the pointer at the end (`end--`).
2. If the sum of the two numbers is less than the target sum
(_i.e_ `start + end < targetSum`), then we need a pair with a larger sum. So, we
increment the pointer at the start (`start++`).

```js
function findSumPairsTwoPointers(inputArray, targetSum) {
  let startPointer = 0;
  let endPointer = inputArray.length - 1;

  while (startPointer < endPointer) {
    let startValue = inputArray[startPointer];
    let endValue = inputArray[endPointer];
    let calculatedSum = startValue + endValue;
    if (calculatedSum === targetSum) {
      return `${startValue} + ${endValue} is ${targetSum}`;
    } else if (calculatedSum > targetSum) {
      endPointer -= 1;
    } else {
      startPointer += 1;
    }
  }
}
```

The time complexity of the above algorithm will be `O(n)`, this is a lot more
desireable. I timed these functions using `console.time` and got the following
result:

```bash
2 + 4 is 6
findSumPairs(): 11.549ms
2 + 4 is 6
findSumPairsTwoPointers(): 0.171ms
```

## An Alternate Approach

An alternative to taking a two-pointer or a binary search approach, would be to
use a hash table. We could iterate through each number in the array such that
`x + y = targetSum`. If we are at number `x` we need to find `y`, we can take the
following steps:

1. Search for `y` by looking for `targetSum - x` in the hash table. If it is there, we have found the pair.
2. Otherwise, insert `x` into the hash table, and continue on.

```js
function findSumPairsHashTable(inputArray, targetSum) {
  const numbers = {};
  for (let i = 0; i < inputArray.length; i++) {
    const x = inputArray[i];
    if (targetSum - x in numbers) {
      return `${inputArray[i]} + ${inputArray[numbers[targetSum - x]]} is ${targetSum}`;
    }
    numbers[x] = i;
  }
}
```

The above algorithm's runtime is also `O(n)`. The only difference is that the
space complexity would be `O(n)` in the worst case, whereas the two pointer
algorithm's space complexity would be `O(1)`.

## Example: Remove Duplicates In-Place

**_Given an array of sorted numbers, remove all duplicates from it. You should not use any extra space; after removing the duplicates in-place return the length of the subarray that has no duplicate in it._**

For example:

```bash
Input: [2, 3, 3, 3, 6, 9, 9]
Output: 4
```

The first four elements after removing the duplicates will be `[2, 3, 6, 9]`.
Since the array is sorted, we can shift the elements left whenever we find a
duplicate. One pointer iterates through the array, and the other pointer for
placing the next non-duplicate number.

The algorithm would be to iterate through the array and whenever we see a
non-duplicate number we move it next to the last non-duplicate number we’ve seen:

```js
function lengthOfDedupedArray(inputArray) {
  let nextNonDuplicate = 1; // index of the next non-duplicate element
  let iteratingPointer = 1;
  while (iteratingPointer < inputArray.length) {
    if (inputArray[nextNonDuplicate - 1] !== inputArray[iteratingPointer]) {
      inputArray[nextNonDuplicate] = inputArray[iteratingPointer];
      nextNonDuplicate += 1;
    }
    iteratingPointer += 1;
  }

  return nextNonDuplicate;
}
```

The runtime is `O(n)` where `n` is the length of the `inputArray`, and the space
complexity is `O(1)` because it is in-place.
