
#### Traversal in a binary tree: 

Traversal meant visiting every node in the list at least once. Traversal has several applications, one might want to visit each node and print their values, another might want to add each of those elements. It is, therefore, crucial to study the techniques of traversal.

But things were easy when we used to traverse through the lists, or the arrays, since they were linear structures, and the directions you choose to traverse were limited, either front to rear or from rear to front. But today we’ll accomplish the complexity of traversing through a non-linear data structure, binary tree.

So basically, we have three different ways to traverse in a binary tree. They are InOrder, PostOrder, and PreOrder Traversals. Let's take a sample tree, and walk through it one by one, using each traversal technique for better understanding.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_1.webp)

Let’s start with the first one.

**PreOrder Traversal in a Binary Tree:**

So in this traversal technique, the first node you start with is the root node. And thereafter you visit the left subtree and then the right subtree. Taking the above example, I’ll mark your order of traversal as below. You first visit section 1, then 2, and then 3.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_2.webp)

Now, this was to give you a general idea of the traverse in a binary tree using PreOrder Traversal. Each time you get a tree, you first visit its root node, and then move to its left subtree, and then to the right.

So, here you first visit the root node element 7 and then move to the left subtree. The left subtree in itself is a tree with root node 11. So, you visit that and move further to the left subtree of this subtree. There you see a single element 7, you visit that, and then move to the right subtree which is a NULL. So, you're finished with the left subtree of the main tree.  Now, you move to the right subtree which has element 2 as its node. And then a NULL to its left and element 9 to its right.

So basically, you recursively visit each subtree in the same order. And your final traversal order is:

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_3.webp)

Here, each block represents a different subtree.

**PostOrder Traversal in a Binary Tree:**

In this traversal technique, things are quite opposite to the PreOrder traversal. Here, you first visit the left subtree, and then the right subtree. So, the last node you’ll visit is the root node. Taking the same above example, I’ll mark your order of traversal as below. You first visit section 1, then 2, and then 3.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_4.webp)

This was again a general idea of you traverse in a binary tree using PostOrder Traversal. Each time you get a tree, you first visit its left subtree, and then its right subtree, and then move to its root node.

I expect you to write the flow of the traversal in PostOrder yourself, and let me know if you could. We would anyway see them in detail.

**Hint:** Your final traversal order should be.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_5.webp)

Here, each block represents a different subtree.

**InOrder Traversal in a Binary Tree:**

In this traversal technique, we simply start with the left subtree, that is you first visit the left subtree, and then go to the root node and then you’ll visit the right subtree. Taking the same above example, I’ll mark your order of traversal as below. You first visit section 1, then 2, and then 3.

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_6.webp)

This was a general idea of you traverse in a binary tree using InOrder Traversal. Each time you get a tree, you first visit its left subtree, and then its root node, and then finally its right subtree.

I expect you to write the flow of the traversal in InOrder yourself, and let me know if you could.

**Hint:** Your final traversal order should be:

![](https://cwh-full-next-space.fra1.digitaloceanspaces.com/videos/data-structures-and-algorithms-in-hindi-66/Image_7.webp)

Here, each block represents a different subtree.

So basically, the names PreOrder, PostOrder, and InOrder were given with respect to the position we keep our root node at while traversing in the Binary Tree. Since we first visit the root node in the first technique, that's why the name PreOrder. And we visit the root node at last in the PostOrder and in between in InOrder. Each of these techniques has one thing in common: the left subtree is traversed before the right subtree.


