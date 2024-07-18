# Dagster Essentials Repository
## Juan S.

### Dagster installation - Poetry
1. `pipx` installation
```shell
brew install pipx
pipx ensurepath
```

2. Poetry Install
> Poetry should always be installed in a dedicated virtual environment to isolate it from the rest of your system. It should in no case be installed in the environment of the project that is to be managed by Poetry. This ensures that Poetry’s own dependencies will not be accidentally upgraded or uninstalled. 

```shell
# 1. Install
pipx install poetry
pipx upgrade poetry # For upgrades

# ~ Optional for oh my zsh
mkdir $ZSH_CUSTOM/plugins/poetry
poetry completions zsh > $ZSH_CUSTOM/plugins/poetry/_poetry
```

3. Poetry Setting up
```shell
# 1. Initialization
poetry init

# 2. Activate env. 
poetry shell

# 3. Install dependencies after setting up toml file.
poetry install
```


### Dagster Initialization
- This particular project initializes from a repo, as example.
```shell
dagster project from-example --example project_dagster_university_start --name dagster_university
```

```shell
cd dagster_university
cp .env.example .env
pip install -e ".[dev]"
```

### Dagster Project Structure
- This is the project structure.

| File/Directory                        | Context    | Description                                                                                                                                                                                                                                                                                       |
|---------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| README.md                             | Python     | A description and starter guide for the Dagster project.                                                                                                                                                                                                                                          |
| dagster_university/                   | Dagster    | A Python module that will contain your Dagster code. This directory also contains the following:                                                                                                                                                                                                  |
|                                       |            | `__init__.py` - This file includes a Definitions object that defines what is loaded in your project, such as assets and sensors. This allows Dagster to load the definitions in a module. We’ll discuss this topic, and this file, later in this course.                                           |
|                                       |            | Several directories, for example: `/assets`. These directories follow our recommended best practices and will be used to contain the definitions - like assets - you create in the following lessons. We’ll discuss the files they contain later, too.                                              |
| dagster_university/init.py            | Dagster    | Each Python module has an `__init__.py`. This root-level `__init__.py` is specifically used to import and combine the different aspects of your Dagster project. This is called defining your Code Location. You’ll learn more about this in a future lesson.                                        |
| dagster_university/assets/constants.py| Dagster U  | A pre-made file with some string constants that you’ll reference for convenience.                                                                                                                                                                                                                 |
| dagster_university_tests/             | Dagster    | A Python module that contains unit tests for dagster_university.                                                                                                                                                                                                                                  |
| data/                                 | Dagster U  | This directory (and directories within it) is where you’ll store the data assets you’ll make during this course. In production settings, this could be Amazon S3 or a data warehouse.                                                                                                             |
| .env                                  | Python     | A text file containing pre-configured environment variables. We’ll talk more about this file in Lesson 6, when we cover connecting to external services.                                                                                                                                           |
| pyproject.toml                        | Python     | A file that specifies package core metadata in a static, tool-agnostic way. This file includes a `tool.dagster` section which references the Python module with your Dagster definitions defined and discoverable at the top level. This allows you to use the `dagster dev` command to load your Dagster code without any parameters. |
| setup.py                              | Python     | A build script with Python package dependencies for your new project as a package. This file is used to specify dependencies.                                                                                                                                                                      |
| setup.cfg                             | Python     | A file that contains option defaults for setup.py commands.                                                                                                                                                                                                                                       |
