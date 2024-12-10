# pytest


```
pytest ...
python -m pytest ...

# verbosity - list tests
python -m pytest -v ...
```


## coverage

```bash
# Pick coverage modules
pytest <tests...> --cov=foo.bar --cov=foo.baz

# Report uncovered lines
pytest <tests...> --cov=foo.bar --cov-report=term-missing
```


## timing

```bash
# Show <n> slowest setups/tests
pytest <tests...> --duration <n>
```
