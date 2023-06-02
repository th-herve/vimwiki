# Track bug with bisect

You can use `git bisect` to track in which commit a bug was introduced.

It works by proposing past commit to the user and asking for feedback (bug present or not).
It then narrow down the commit that cause the bug with `binary search`.

## Basic use

1. Get the `hash` of a commit where the bug is not present
    > git log

2. Start the `bisect`
    > git bisect start

3. Give it the `hash` of the good commit.
    > git bisect good (hash)

4. If the current commit has the bug, no need to enter a hash here
    > git bisect bad <optional hash>

5. Test in the app if the bug is present, and give `feedback`
- If present
    > git bisect bad
- If not present
    > git bisect good
     
>Note: if you made a mistake, you can change the state (good|bad) of a commit:
    > git bisect (good|bad) (hash)

6. Repeat step 5, when done, the commit causing the bug will be identified

7. After a bisect session, you need to return to a working commit.
- Go to the original head commit (most recent commit)
    > git bisect reset
- Or go to a given commit
    > git bisect reset (hash)

## Other command

| name           | action                                             |
|----------------|----------------------------------------------------|
| git bisect log | show what has been done, what's marked good or bad |

> Note: this process can be fully automated, and check by itself if a bug is present or not. (but how???) 
