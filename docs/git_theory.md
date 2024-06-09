# Git theory


unstaged -> stage -> commit

Git is an `acyclic graph`:
- each commit is a node in the graph.
- each pointer is the child to parent relationship


All repo as the `.git` directory. Delete it and there is no more repo.

## Git internal representation

Git stores a copy of each commited files and directory int the `.git` directory.

### sha

Git object are named with a sha (hash)

Based on what's commited, time, user name...

Object exist in the `.git/objects` directory. The fist two characters of the sha are the directory name and the remaining the file.
Example with the sha : 891274b8aae0cb757a967c3809d462b4da781302
It would be stored as .git/objects/89/1274b8aae0cb757a967c3809d462b4da781302

### Objects

#### Commits



#### Tree

A directory representing a directory in the project. Contains files and other directory.

> note: since a directory is represented by a tree and not a blob, we can commit an empty directory.

#### Blob

Stand for `Binary Large Objects`.

Represents file contents without metadata.

#### sha/tree/blob

A sha contains a tree, that contains one or more blobs that each contain the content of files tracked.

We can follow this but using the command `git cat-file -p <sha>` that gives the code of the tree then `git cat-file -p <tree>` that gives the code of the blobs.

`->` git does not store diffs. It stores the entire source at the point of each commit. But if there is no difference in a file. The blob corresponding reference the last time it was modified.

## Ref directory

The ref directory stores, in the `heads` directory, the branches names and the commit they point to.

A branch is a pointer to a commits.

## Internal commands

```bash
git show --pretty=raw <sha> # shows info on an object
git ls-tree <tree sha> # show content of a tree
```



