# Balance binary search tree

A binary search tree is balanced if:
 - The height of the left and right tree for any node does not differ by more than 1
 - The left subtree of that node is also balanced
 - The right subtree of that node is also balanced

```markdown
arr = [1, 2, 3, 4, 5, 6, 7]

        5
       / \
      2   6
     / \ / \
    1  3 5  7
```

## Algorithm

1. Initialize start = 0, end = length of the array - 1
2. mid = (start+end) / 2
3. create tree node with mid as root
4. Recursively:
  1. Calculate mid of left subarray and make it root of left subtre of A
  1. Calculate mid of right subarray and make it root of right subtre of A
