# 🌳 Binary Trees Project

<p align="center">
  <img src="https://apply.holbertonschool.com/holberton-logo.png" alt="Holberton School Logo" width="300">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C-Programming-blue.svg" alt="C Language">
  <img src="https://img.shields.io/badge/Holberton-School-red.svg" alt="Holberton School">
  <img src="https://img.shields.io/badge/Data%20Structures-Binary%20Trees-success.svg" alt="Binary Trees">
</p>

<p align="center">
  <strong>A complete implementation of Binary Trees in C</strong><br>
  
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Data Structures](#-data-structures)
- [Learning Objectives](#-learning-objectives)
- [Repository Structure](#-repository-structure)
- [Tasks Overview](#-Tasks-Overview)
- [Examples](#-examples)
- [Authors](#-authors)

---

## 📌 Overview
This project implements various operations and algorithms for binary trees in the C programming language. Binary trees are fundamental data structures in computer science used for efficient data storage, retrieval, and manipulation. This project covers creation, traversal, measurement, and analysis of binary trees.


---

## 🏗️ Data Structures

```c
/**
 * struct binary_tree_s - Binary tree node
 *
 * @n: Integer stored in the node
 * @parent: Pointer to the parent node
 * @left: Pointer to the left child node
 * @right: Pointer to the right child node
 */
struct binary_tree_s
{
    int n;
    struct binary_tree_s *parent;
    struct binary_tree_s *left;
    struct binary_tree_s *right;
};

typedef struct binary_tree_s binary_tree_t;
typedef struct binary_tree_s bst_t;
typedef struct binary_tree_s avl_t;
typedef struct binary_tree_s heap_t;
```
---

## 🎯 Learning Objectives

Upon completion of this project, you should be able to explain:

What is a binary tree and its properties

Differences between binary trees and Binary Search Trees (BST)

Time complexity advantages compared to linked lists

Depth, height, and size of binary trees

Different tree traversal methods (pre-order, in-order, post-order)

Types of binary trees: complete, full, perfect, balanced

---
## Repository Structure 📁 
```
holbertonschool-binary_trees/
├── binary_trees.h
├── 0-binary_tree_node.c
├── 1-binary_tree_insert_left.c
├── 2-binary_tree_insert_right.c
├── 3-binary_tree_delete.c
├── 4-binary_tree_is_leaf.c
├── 5-binary_tree_is_root.c
├── 6-binary_tree_preorder.c
├── 7-binary_tree_inorder.c
├── 8-binary_tree_postorder.c
├── 9-binary_tree_height.c
├── 10-binary_tree_depth.c
├── 11-binary_tree_size.c
├── 12-binary_tree_leaves.c
├── 13-binary_tree_nodes.c
├── 14-binary_tree_balance.c
├── 15-binary_tree_is_full.c
├── 16-binary_tree_is_perfect.c
├── 17-binary_tree_sibling.c
├── 18-binary_tree_uncle.c
└── README.md
```
---
## 📝 Tasks Overview
```
Task 0: New Node
Function: binary_tree_t *binary_tree_node(binary_tree_t *parent, int value)
Creates a new binary tree node with given value and parent.

Task 1: Insert Left
Function: binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value)
Inserts a node as the left-child of another node. If parent already has a left child, the new node takes its place.

Task 2: Insert Right
Function: binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value)
Inserts a node as the right-child of another node. If parent already has a right child, the new node takes its place.

Task 3: Delete
Function: void binary_tree_delete(binary_tree_t *tree)
Deletes an entire binary tree using post-order traversal.

Task 4: Is Leaf
Function: int binary_tree_is_leaf(const binary_tree_t *node)
Checks if a node is a leaf (has no children).

Task 5: Is Root
Function: int binary_tree_is_root(const binary_tree_t *node)
Checks if a node is a root (has no parent).

Task 6: Pre-order Traversal
Function: void binary_tree_preorder(const binary_tree_t *tree, void (*func)(int))
Traverses tree using pre-order (Root → Left → Right).

Task 7: In-order Traversal
Function: void binary_tree_inorder(const binary_tree_t *tree, void (*func)(int))
Traverses tree using in-order (Left → Root → Right).

Task 8: Post-order Traversal
Function: void binary_tree_postorder(const binary_tree_t *tree, void (*func)(int))
Traverses tree using post-order (Left → Right → Root).

Task 9: Height
Function: size_t binary_tree_height(const binary_tree_t *tree)
Measures the height of a binary tree (longest path from root to leaf).

Task 10: Depth
Function: size_t binary_tree_depth(const binary_tree_t *tree)
Measures the depth of a node (distance from root).

Task 11: Size
Function: size_t binary_tree_size(const binary_tree_t *tree)
Counts the total number of nodes in a tree.

Task 12: Leaves
Function: size_t binary_tree_leaves(const binary_tree_t *tree)
Counts the number of leaf nodes in a tree.

Task 13: Nodes
Function: size_t binary_tree_nodes(const binary_tree_t *tree)
Counts nodes with at least one child.

Task 14: Balance Factor
Function: int binary_tree_balance(const binary_tree_t *tree)
Calculates the balance factor of a tree (height(left) - height(right)).

Task 15: Is Full
Function: int binary_tree_is_full(const binary_tree_t *tree)
Checks if a binary tree is full (every node has 0 or 2 children).

Task 16: Is Perfect
Function: int binary_tree_is_perfect(const binary_tree_t *tree)
Checks if a binary tree is perfect (full and all leaves at same level).

Task 17: Sibling
Function: binary_tree_t *binary_tree_sibling(binary_tree_t *node)
Finds the sibling of a node (other child of same parent).

Task 18: Uncle
Function: binary_tree_t *binary_tree_uncle(binary_tree_t *node)
Finds the uncle of a node (sibling of parent).
```
---
## 📊 Examples

### Creating a Tree
```c
binary_tree_t *root = binary_tree_node(NULL, 98);
root->left = binary_tree_node(root, 12);
root->right = binary_tree_node(root, 402);
binary_tree_insert_left(root->right, 128);
binary_tree_insert_left(root, 54);
```
### Tree Visualization
```
       .-------(098)-------.
  .--(054)       .--(402)--.
(012)          (128)     (512)
```
### Traversal Output
```
Pre-order:  98, 54, 12, 402, 128, 512
In-order:   12, 54, 98, 128, 402, 512
Post-order: 12, 54, 128, 512, 402, 98
```
--- 
## 👥 Authors

<div align="center">

### **Project Developers**

| **Solaf Alessa** | **Abdullah Aldaghaym** |
|:----------------:|:----------------------:|
| [![GitHub](https://img.shields.io/badge/📁_GitHub-Profile-black?style=for-the-badge&logo=github)](https://github.com/lilsouy) | [![GitHub](https://img.shields.io/badge/📁_GitHub-Profile-black?style=for-the-badge&logo=github)](https://github.com/abdullahaldaghaym) |
| **C Developer** | **C Developer** |

</div>
