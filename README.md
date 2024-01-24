# sphinx-docs

Documentation containing designs, guides, and notes.

## dependencies

| name                                       | description                                |
|--------------------------------------------|--------------------------------------------|
| [pyenv](https://github.com/pyenv/pyenv)    | python version management                  |
| [poetry](https://github.com/python-poetry) | python packaging and dependency management |

## install

development:
```shell
poetry install
poetry shell
pre-commit install
```

production:
```shell
poetry install --without dev
```

## build

> [!IMPORTANT]  
> `src/sphinx-docs` is not currently used.

package:
```shell
poetry build
```

## usage

test:
```shell
tox run
```

doc:
```shell
make -C docs html
```

check:
```shell
pre-commit run
```
