> Trees 
> > In this tutorial, we’ll be covering Binary Trees, Binary Search Trees, and K-ary Trees. We will review some common terminology that is shared amongst all of the trees and then dive into specifics of the different types.

> Common Terminology
> Node - A Tree node is a component which may contain it’s own values, and >       references to other nodes
 Root - The root is the node at the beginning of the tree
 K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
 Left - A reference to one child node, in a binary tree
 Right - A reference to the other child node, in a binary tree
 Edge - The edge in a tree is the link between a parent and child node
 Leaf - A leaf is a node that does not have any children
 Height - The height of a tree is the number of edges from the root to the furthest leaf

 ![alt](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)


 > Traversals
An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:

> Depth First
> Breadth First
> Depth First
> Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:

> Pre-order: root >> left >> right
In-order: left >> root >> right
Post-order: left >> right >> root


![alt](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/tree-example.png)


>  `Pre-order
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
In-order
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
Post-order
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value`
    
    > Output: A, B, C, D, E, F

Traditionally, breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree. Let’s break down the process.

Given our starting tree shown above, let’s start by putting the root into the queue:


> Adding a node
Because there are no structural rules for where nodes are “supposed to go” in a binary tree, it really doesn’t matter where a new node gets placed.

> One strategy for adding a new node to a binary tree is to fill all “child” spots from the top down. To do so, we would leverage the use of breadth first traversal. During the traversal, we find the first node that does not have all it’s children filled, and insert the new node as a child. We fill the child slots from left to right.

> In the event you would like to have a node placed in a specific location, you need to reference both the new node to create, and the parent node upon which the child is attached to.

> Big O
The Big O time complexity for inserting a new node is O(n). Searching for a specific node will also be O(n). Because of the lack of organizational structure in a Binary Tree, the worst case for most operations will involve traversing the entire tree. If we assume that a tree has n nodes, then in the worst case we will have to look at n items, hence the O(n) complexity.

> The Big O space complexity for a node insertion using breadth first insertion will be O(w), where w is the largest width of the tree. For example, in the above tree, w is 4.

> A “perfect” binary tree is one where every non-leaf node has exactly two children. The maximum width for a perfect binary tree, is 2^(h-1), where h is the height of the tree. Height can be calculated as log n, where n is the number of nodes.

> Binary Search Trees
A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

Here is how we would change our Binary Tree example into a Binary Search Tree: