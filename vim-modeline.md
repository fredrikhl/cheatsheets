# modeline

Use modelines to hard-code vim settings for a given file:

```
# vim: set ts=4 sw=0 sts=0 expandtab:
```

## settings

- `ft`, `filetype`
- `tw`, `textwidth`: line width for wrapping
- `ts`, `tabstop`: size of an actual `\t`, for alignment
- `sw`, `shiftwidth`: size of an indent (used in dedent/indent ops, set to 0 to use `ts`)
- `sts`, `softtabstop`: size of a single `\t` on insert (usually set to 0/-1)
- `expandtab`: insert *soft tabs* (spaces) in place of a tab char
- `noexpandtab`: insert acual `\t` - tabs
