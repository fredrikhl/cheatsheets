# git gc

local git repo optimization and cleanup

```bash
git gc
```

## aggressive

`git gc` will pack objects into archives.  Use `--aggressive` to force a full
repack of existing archives.  This option is pretty expensive compared to a
regular `git gc`.  See `git repack` for more info.

```bash
git gc --aggressive
```

## prune

`git gc` will prune unreachable objects older than `2.weeks.ago`.  Change the
date offset with `--prune`.  See `git prune --expire` for more info.

```bash
git gc --prune=now
git gc --prune=1.day.ago
git gc --prune=1.week.ago
```
