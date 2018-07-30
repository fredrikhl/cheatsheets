# Yaml multiline syntax

Block indicator: `[|>][-+]?[0-9]?`

- Block Style Indicators
  - `|` - literal, keep newlines
  - `>` - folded, replace newlines with spaced, reduce double newline to single.
- Block Chomping Indicators
  - ` ` - default, single newline at end
  - `-` - strip, remove all newline after the end of the string
  - `+` - keep all newlines
- Indentation Indicators
  - `[|>]` - default, use indentation of next line
  - `[|>]N` - use `N` spaces for indentation.

## Replace newlines with spaces (folded)

```yml
example: >
  Lorem ipsum
  dolor sit amet,
  consectetur adipiscing elit,
  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
> incididunt ut labore et dolore magna aliqua.
>

## Keep all newlines, including at the end

```yml
example: |+
  Lorem ipsum
  dolor sit amet,
  consectetur adipiscing elit,
  sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 

```

> Lorem ipsum
> dolor sit amet,
> consectetur adipiscing elit,
> sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
>
>
