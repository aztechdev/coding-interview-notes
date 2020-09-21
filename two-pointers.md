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
of elements in the input array. How could we make this more efficient?

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
