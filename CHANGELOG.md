## v0.2.0 (2026-04-04)

### Feat

- add pytest and pytest-coverage checks to project requirements
- configure pre-commit tools and src in pyproject
- **.pre-commit-config.yaml**: add a comprehensive suite of pre-commit hooks
- **pyproject.toml**: add commitizen and pre-commit as dev dependencies
- add pyproject, README and a template script

### Fix

- replace incorrect allow-no-tests pytest flag with a simple placeholder test
- **pyproject.toml**: add missing pip-audit CI requirement to dev dependencies

### Refactor

- move pytest configuration from CI into pyproject.toml
- **.pre-commit-config.yaml**: alter pre-commit hooks to remove excessive hooks
- **src**: move python files and assets into a dedicated src folder
