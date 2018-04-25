# pypi config


## upload

```ini
# ~/.pypirc

[distutils]
index-servers =
    pypi
    pypi-test
    nexus-docker

[pypi]
repository: https://upload.pypi.org/legacy/
username: <username>

[pypi-test]
repository: https://test.pypi.org/legacy/
username: <username>

[nexus-docker]
repository = http://localhost/repository/local/
username = admin
password = admin123
```

```bash
python setup.py <build-type> upload -r <index-name>
```


## download

Config order:

1. site-wide file (`/etc/pip.conf`, `/Library/Application Support/pip/pip.conf`)
2. per-user file (`~/.config/pip/pip.conf`, `~/.pip/pip.conf`)
3. virtualenv-specific (`<venv>/pip.conf`)

```ini
# ~/.config/pip/pip.conf
[global]
index = https://pypi.python.org/pypi
index-url = https://pypi.python.org/simple
# index = http://localhost/repository/local/pypi
# index-url = http://localhost/repository/local/simple
```
