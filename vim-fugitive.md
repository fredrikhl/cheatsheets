# vim-fugitive

## Gblame

```
:Gblame [flags] 
    Run git-blame on the file and open the results in a
    scroll bound vertical split.  You can give any of
    ltfnsewMC as flags and they will be passed along to
    git-blame.  The following maps, which work on the
    cursor line commit where sensible, are provided:

      g?    show this help
      A     resize to end of author column
      C     resize to end of commit column
      D     resize to end of date/time column
      q     close blame and return to blamed window
      gq    q, then |:Gedit| to return to work tree version
      <CR>  q, then open commit
      o     open commit in horizontal split
      O     open commit in new tab
      p     open commit in preview window
      -     reblame at commit
      ~     reblame at [count]th first grandparent
      P reblame at [count]th parent (like HEAD^[count])
```

To close a buffer: C-w q
