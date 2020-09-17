# Big O Notation

The definition below is from the Wikipedia article on [Big O notation](https://en.wikipedia.org/wiki/Big_O_notation).

> In computer science, big O notation is used to classify algorithms according
> to how their run time or space requirements grow as the input size grows.

In my university degree, this type of notation was also referred to as "asymptotic notation".
For the purposes of runtime analysis in competitive programming and interviews,
Big O is used to describe the worst case scenario for solutions.

Big O is used to classify algorithms using what is called "[computational complexity theory](https://en.wikipedia.org/wiki/Computational_complexity_theory)".
What is most commonly used to describe an algorithm is its "[time complexity](https://en.wikipedia.org/wiki/Time_complexity)",
which is the computational complexity that describes the amount of time it takes
to run an algorithm.

In a [video with Gayle Laakmann McDowell](https://youtu.be/v4cd1O4zkGw), she
provides four simple rules when trying to figure out an algorithm's time complexity:

Rule 1: **Different steps get added**. For example, if you have one step that takes
`O(a)` time and a second step that takes `O(b)` time, the full algorithm would be
`O(a+b)`:

```js
function something() {
  doStep1(); // O(a)
  doStep2(); // O(b)
}
```

Rule 2: **Drop constants**. In the below example, one algorithm finds the min
element in an array, then the max element. The second algorithm finds both simultaneously.
These are both described as `O(n)` where `n` is the length of the array:

```js
function minMax1(array) {
  let min = 0;
  let max = 0;
  for (let i=0; i < array.length; i++) { // O(n)
    min = Math.min(array[i], min);
  }
  for (let i=0; i < array.length; i++) { // O(n)
    max = Math.max(array[i], max);
  }
}

// versus

function minMax2(array) {
  let min = 0;
  let max = 0;
  for (let i=0; i < array.length; i++) { // O(n)
    min = Math.min(array[i], min);
    max = Math.max(array[i], max);
  }
}
```

How is the `minMax1` function `O(n)`? To add up the runtime, `O(n) + O(n) = O(2n)`,
but we drop the constant (`2` in this case) to get `O(n)` because we are looking
for how the algorithm scales roughly (_i.e._ is it linear? Is it quadratic?).

<!-- TODO: -->
Rule 3: TODO (I gotta go to sleep)