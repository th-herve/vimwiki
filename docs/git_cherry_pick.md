# Cherry pick

The `git cherry-pick` command allows to apply one or several commit
from one branch to another, without merging the two branch.

It creates a new commit in the branch it's apply to, with the same message
of the commit in the other branch.

## Example

If we have two branches, main and dev. The dev branch has a bug fix commit
we want to apply to the main, but we don't want to apply the rest of the commit.

```markdown
    main
     O
     ⎜
     O  dev
     ⎜ \
     O  O
     ⎜  ⎜
     O  O  <- bug fix
        ⎜
        O
```

1. Get the commit hash of the bug fix with `git log`
2. Be sure to be on the branch to apply the new commit, in this case `main`
3. Run
  > git cherry-pick (bug fix hash)

```markdown
          main
           O
           ⎜
           O  dev
           ⎜ \
           O  O
           ⎜  ⎜
           O  O  <- bug fix
           ⎜  ⎜
 bug fix ->O  O
```
## For multiple commit

Simply specify multiple commit hash

> git cherry-pick hash1 hash2

It create a new commit for each hash, applying the changes in the order
specify in the command.

## Resolve merge conflict

Cherry pick can produce merge conflicts.

To resolve:

1. run `git status` to see the files that need resolution.

[source](https://www.youtube.com/watch?v=i657Bg_HAWI)
