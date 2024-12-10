# coverage

```bash
coverage run [coverage-options] <script> [script-options]
coverage run [coverage-options] -m module [module-options]
```


## report

```bash
coverage report --include "Cerebrum/modules/ad2/*" -m
```


## pytest

To use coverage in `pytest`:

```bash
# pick modules to measure coverage of
pytest <tests...> --cov=foo.bar --cov=foo.baz

# report uncovered lines in modules
pytest <tests...> --cov=foo.bar --cov-report=term-missing
```
