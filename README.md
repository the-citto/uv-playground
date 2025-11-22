# UV playground
> Astral will eventually move to some commercial approach, hopefully something similar to Docker and not to Anaconda. 
> They promised to keep their tools open source, for the time being is no concern. 

## Zero to hero
<details>
<summary>Notes</summary>

### Good regular practice
```bash
uv python upgrade
```

### Start package project
```bash
uv init --package --python 3.13
```

> either `uv init <package-name> && cd <package-name>`
> or `mkdir <package-name> && cd <package-name> && uv init`
> 
> the second is convenient when git has already been initialized

### Add dependency groups
```bash
uv add --group test pytest pytest-cov pyright[nodejs] mypy ruff flake8 black isort ty
```
```bash
uv add --dev ipython
```

</details>

## Files

### Tools
Append tools to `pyproject.toml`
```bash
wget https://raw.githubusercontent.com/the-citto/uv-playground/refs/heads/main/tools-pyproject.toml -q -O - >> pyproject.toml
```
`ty` settings coming soon

### Python .gitignore
Overwrite `.gitignore` with full python GitHub template:
```bash
wget https://github.com/github/gitignore/raw/refs/heads/main/Python.gitignore -O .gitignore
```
### MIT License
Overwrite MIT License with GitHub template:
```bash
wget https://raw.githubusercontent.com/licenses/license-templates/refs/heads/master/templates/mit.txt \
    -q -O - \
    | sed -e "s/{{ year }}/$(date +%Y)/" \
    | sed -e "s/{{ organization }}/$(git config user.name)/" \
    > LICENSE
```
