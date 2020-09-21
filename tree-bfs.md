# Tree Breadth First Search Pattern

Any problem involving the traversal of a tree in a **level-by-level** order can
be efficiently solved using **Breadth First Search (BFS)**. We make use of the
**queue** data structure to keep track of the nodes in a level before going to
the next level in the tree. The most basic problem statement goes:

**_Given a binary tree, populate an array to represent its level-by-level traversal. You should populate the values of all nodes of each level from left to right in separate sub-arrays._**

In order to print out a binary tree (left children first), we can apply the BFS
algorithm:

1. Push the `root` node to the queue (enqueue)
2. We want to keep iterating until the queue is empty
3. We want to group by level, so we keep track of how many nodes are on a level using the length of the queue
4. In each iteration of this inner loop (based on the level size), remove a node from the queue (dequeue)
5. Push this node's value to an array representing the values at that level
6. If the node has a child on the left, add the child node to the queue
7. If the node has a child on the right, add the child node to the queue
8. Add the array of values for this level to the result. Repeat Steps 2-7 until the queue is empty

```js
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

function traverse(root) {
  result = [];
  if (!root) {
    return result;
  }

  let nodeQueue = [];
  nodeQueue.unshift(root); // add to front of array

  while (nodeQueue.length > 0) {
    let levelSize = nodeQueue.length;
    let currentLevelValues = [];
    for (let i = 0; i < levelSize; i++) {
      let currentNode = nodeQueue.pop(); // remove from back of array
      currentLevelValues.push(currentNode.value);
      if (currentNode.left) {
        nodeQueue.unshift(currentNode.left);
      }
      if (currentNode.right) {
        nodeQueue.unshift(currentNode.right);
      }
    }
    result.push(currentLevelValues);
  }

  return result;
}


const root = new TreeNode(12);
root.left = new TreeNode(7);
root.right = new TreeNode(1);
root.left.left = new TreeNode(9);
root.right.left = new TreeNode(10);
root.right.right = new TreeNode(5);
console.log(`Level order traversal: ${traverse(root)}`);
```

The above algorithm has a runtime of `O(n)`, where `n` is the number of nodes in
the tree (because we visit each node).
