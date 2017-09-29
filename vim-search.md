# vim: search

## search

* Search word under cursor: [ * ]
* Search for complete word: `\<foo\>`


## search and replace

Replace using last search: ``s//bar/``


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
