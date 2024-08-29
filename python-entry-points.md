# entry points in python


## Create entrypoints using setuptools

Case - Provide extra lexers for *pygments*:

```python
setup(
    name="my_pkg",
    entry_points={
        "pygments.lexers": [
            "foo = my_pkg.lexers:FooLexer",
            "bar = my_pkg.lexers:BarLexer",
        ],
    },
)
```


## Fetching entrypoints using `pkg_resources`

Example: Find a suitable lexer plugin for *pygments*:

```python
def find_lexer(ext):
    for ep in pkg_resources.iter_entry_points("pygments.lexers",
                                              name=content_type):
        try:
            return ep.load()
        except:
            continue
    raise NotImplementedError("No parser found")
```


Installing a plugin using `setuptools`:


## Fetching entrypoints using `importlib`

Example: Find a suitable lexer plugin for *pygments*:

```python
def find_lexer(content_type):
    for ep in entry_points(name=content_type, group="pygments.lexers"):
        try:
            return ep.load()
        except Exception:
            continue
    raise NotImplementedError("No lexerfound")
```
