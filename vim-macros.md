# vim - macros

Record key sequence in normal mode, replay in normal mode.

Macros are stored in registers a-z.


- Start recording: `q<letter>`
- Finish recording: `q`
- Replay: `@<letter>` or `<number>@<letter>`
- Repeat: `@@` or `<number>@@`

## Accessing macros in command mode

Macros are sequences of key-presses, stored as strings in a register:

```vim
" inspect macro 'x'
register x

" set a macro key sequence 'x'
let @x='hk'
```

## More

```vim
help recording
help getreg()
help setreg()
```
