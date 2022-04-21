# git worktree

## worktree name

Worktree names (`<worktree>`) is the actual path to the worktree, or
the least required part of the pathname tail to make it unique.

A worktree at e.g.  `/path/to/tree` can be identified as:

- `tree`
- `to/tree`
- `path/to/tree`
- `/path/to/tree`


## new worktree

```bash
git worktree add [-b <new-branch>] /path/to/tree [<from-commit-ish>]
```


## list worktrees

```bash
git worktree list
```

Note: `git status` highlights branches that are checked out in other worktrees.


## remove worktree

```bash
git worktree remove <worktree>
```
