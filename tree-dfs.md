# Tree Breadth First Search Pattern

Any problem involving the traversal of a tree in a **root-to-leaf** order can
be efficiently solved using **Depth First Search (DFS)**. We can make use of the
**stack** data structure to keep track of the nodes in a branch before going to
the next branch in the tree.

We will be using recursion (or we can also use a stack for the iterative approach)
to keep track of all the previous (parent) nodes while traversing. This also
means that the space complexity of the algorithm will be `O(H)`, where `H` is
the maximum height of the tree. The most basic problem statement goes:

**_Given a binary tree and a number `S`, find if the tree has a path from root-to-leaf such that the sum of all the node values of that path equals `S`._**

To recursively traverse a binary tree in a DFS fashion, we can start from the
root and at every step, make two recursive calls one for the left and one for
the right child.

1. Start DFS with the root of the tree
2. If the current node is not a leaf node, do two things:
   * Subtract the value of the current node from the given number to get a new sum (_i.e._ `S` = `S` - `node.value`)
   * Make two recursive calls for both the children of the current node with the new `S` calculated in the above step
3. At every step, see if the current node is a leaf node, and if its value is equal to the given `S`.
If both of these conditions are true, we have found the root-to-leaf path, so we return `true`
4. If the current node is a leaf but its value is not equal to the given `S`, return `false`

> If `node.left === null && node.right === null`, then `node` is a leaf.

```js
class TreeNode {
  constructor(val, left = null, right = null) {
    this.val = val;
    this.left = left;
    this.right = right;
  }
}

function hasPath(root, sum) {
  if (root === null) {
    return false;
  }

  // if the current node is a leaf and its value is equal to the sum, we've found a path
  if (root.val === sum && root.left === null && root.right === null) {
    return true;
  }

  // recursively call to traverse the left and right sub-tree
  // return true if any of the two recursive call return true
  return hasPath(root.left, sum - root.val) || hasPath(root.right, sum - root.val);
}

const root = new TreeNode(12);
root.left = new TreeNode(7);
root.right = new TreeNode(1);
root.left.left = new TreeNode(9);
root.right.left = new TreeNode(10);
root.right.right = new TreeNode(5);
console.log(`Tree has path: ${hasPath(root, 23)}`);
console.log(`Tree has path: ${hasPath(root, 16)}`);
```

The above algorithm has a runtime of `O(n)`, where `n` is the number of nodes in
the tree (because we visit each node).
