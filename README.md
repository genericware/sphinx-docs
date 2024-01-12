# sphinx-docs

Documentation on projects, designs, guides, etc.

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
> `src/docs` is not currently used.

package:
```shell
poetry build
```

## run

test:
```shell
pytest .
```

coverage:
```shell
coverage run -m pytest && coverage report -m
```

matrix:
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

format:
```shell
black .
```

lint:
```shell
ruff .
```

type:
```shell
mypy .
```
