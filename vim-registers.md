# vim - registers

Yank to/put from specific register

* `"<letter>y`
* `"<letter>p`

List registers

* All: `:reg`
* Selection: `:reg [letters...]`


Reference register:

* `echo @1`
" `let @1='foo'`


Put in insert mode: `<c-r> <letter>`


## special

### `"` - default register

```vim
" set the default register
let @"='something to paste with [p]'
```

### `/` - hls register

```vim
" set the hls
let @/='substring'
let @/='\<phrase with word boundry\>'
```
