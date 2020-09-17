# The Sliding Window Pattern

In many problems dealing with an array (or a LinkedList), we are asked to find
or calculate something among all the contiguous subarrays (or sublists) of a
given size. For an example:

**_Given an array, find the average of all contiguous subarrays of size `K` in it._**

A **brute-force** approach would be:

1. Start at index `0` and sum the first `K` items together
2. Divide this sum by `K` to get the average
3. Move to index `1` and repeat

> Make sure to not go past the end of the array: index <= array.length - K

```js
function getAveragesOfSubarrays(K, arrayOfNumbers) {
  const result = [];
  for (let i = 0; i <= arrayOfNumbers.length - K; i++) {
    let sum = 0.0;
    for (let j = i; j < i + K; j++) {
      sum += arrayOfNumbers[j];
    }
    result.push(sum / K);
  }

  return result;
}

const result = getAveragesOfSubarrays(3, [2, 5, 7, 3, -1, 8, 1, 4, -2]);
console.log(`Averages of subarrays of size K: ${result}`);
```

Given that the array is of length `N`, we are calculating the sum of every
element's next `K` elements. Therefore, the time complexity of the algorithm
would be **O(N∗K)**. The time complexity of this algorithm is not great, but
that's to be expected with a brute-force algorithm/naïve solution.

The inefficiency is that for any two consecutive subarrays of size `K`, there
are `K-1` items that are in both (overlap) and will be evaluated twice. Perhaps
there is a way to reuse the sum that has been calculated for the overlapping items.

The efficient solution is to visualize each contiguous subarray as a **sliding window**
of `K` items. We can reuse the sum from the previous subarray by subtracting the
element outside of the window and adding the element now inlcuded within the
sliding window.

```js
function getAveragesOfSubarrays(K, arrayOfNumbers) {
  const result = [];
  let windowSum = 0.0, windowStart = 0;
  for (let windowEnd = 0; windowEnd < arr.length; windowEnd++) {
    windowSum += arrayOfNumbers[windowEnd]; // add the next element
    // slide the window, we don't need to slide if we've not hit the required window size of 'k'
    if (windowEnd >= K - 1) {
      result.push(windowSum / K); // calculate the average
      windowSum -= arrayOfNumbers[windowStart]; // subtract the element going out
      windowStart += 1; // slide the window ahead
    }
  }

  return result;
}
```

Now that we don't have to go through every subarray (of size K) to find the sum,
the complexity is now **O(N)**.
