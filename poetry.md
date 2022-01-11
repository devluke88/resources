---
coverY: 0
---

# Poetry

## Install

```
// Some code
```

## Usage

```
# Create new project with command: poetry new [project_name]
poetry new poetry-demo

# Example directory structure
poetry-demo
├── pyproject.toml
├── README.rst
├── poetry_demo
│   └── __init__.py
└── tests
    ├── __init__.py
    └── test_poetry_demo.py
    
# or you can create folder then go inside and initialise poetry which will create pyproject.toml
poetry init

# Go to directory
cd poetry-demo

# now you can add dependency, for example:
poetry alembic

#this will add dependency in pyproject.toml file

# new shell
poetry shell
exit

# manual activation
source {path_to_venv}/bin/activate
deactivate

source`poetry env info --path`/bin/activate

installing dependency
poetry install

```
