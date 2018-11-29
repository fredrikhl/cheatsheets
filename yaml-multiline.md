# Yaml multiline syntax

* <https://yaml-multiline.info/>
* <https://github.com/wolfgang42/yaml-multiline>


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


## Line continuation

```yml
example: "foo\
    bar\
    baz"
```

> foobarbaz

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
