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

