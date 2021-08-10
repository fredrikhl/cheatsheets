# vim - search

## regular searchsearch

* Search word under cursor: [ * ]
* Search for complete word: `\<foo\>`
* clear highlight: `let @/=''`


## search and replace

Replace using last search: ``s//bar/``

Step-through replacement on regular search result buffer: `cgn` on a match and
escape back to normal mode.  Now `.` can be used to repeat this on other
matches.


### Modifiers

* Confirmation: `s/foo/bar/c`
* Case Insensitive: `s/foo/bar/I`


### markers

Use markers (`\zs`, `\ze`) to replace partial search expression. To replace
'and' with 'or': `s/foo \zsand\ze bar/or/`


## eval context (\\=)

### generate replacement sting from eval context: `\=`

```
s,[a-z]\+,\=strlen(submatch(0)),g
```


### replace space-indent with tab-indent

```
s:\([ ]\{4\}\)\+:\=repeat("\t", len(submatch(0)) / len(submatch(1))):
```
