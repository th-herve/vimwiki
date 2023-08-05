# Binary search tree

`Binary search tree` or BST allows to maintain a `sorted` list of
`number`. It can be created from an `unordered array`.

Each node has a maximum of two children.

It can be use to search for the a number in `O(log(n))`.

`!!`It's not the same as a binary tree, the three difference are:

- All nodes on the left are less than the root node
- All nodes on the right are more than the root node
- All subtree of each node have the two above properties


```markdown
        8
      /   \
     3     10
    / \
   1   6 
      /
     4
```
Note: in the example above, if we replace the last 4 by a 2, it is
not longer a binary search tree. Because the 2 would be on the right 
of the 3 two node above. A smaller value can't be on the right of a node.

## Operations

### Search

The search of a number rely on the fact that if the number is
smaller than the root, it is in the left subtree. And if bigger,
in the right subtree.

```C
if root == NULL
  return NULL;
if number == root->data
  return root->data;
if number < root->data
  return return search(root->left);
if number > root->data
  return return search(root->rigth);
```

### Insertion

Insertion is similar to search, we traverse the tree going left
or right depending on the root. If a subtree is null, we put the node here.

```C
if node == NULL
  return createNode(data);
if data < node->data
  node->left = insert(node->left, data);
else if data > node->data
  node->right = insert(node->right, data);
return node;
```
The `return node` at the end ensure that elements don't lose their
position on the upward recusion step.

### Deletion

TODO (look the source)

## Construction

To create a binary search tree from an array.

For this array: [5, 7, 1, 15, 2]

```markdown
arr[0] become the root node

        5
        
since 7 > 5 it goes on the right

        5
         \
          7
          
1 < 5 it goes on the left

        5
       / \
      1   7
      
15 > 5 -> 15 > 7 it goes to the right of both 

        5
       / \
      1   7
           \
            15
            
9 > 5 -> 9 > 7 -> 9 < 15

        5
       / \
      1   7
           \
            15
           /
          9
          
2 < 5 -> 2 > 1

        5
       / \
      1   7
       \   \
        2   15
           /
          9
```




[source](https://www.programiz.com/dsa/binary-search-tree)
