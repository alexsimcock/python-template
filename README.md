# Python Template

## Getting Started

### Repo Setup

After creating a new repository from this template, complete the following steps before writing any code.

**1. Rename the project in `pyproject.toml`**

Replace every reference to `python-template` with your actual project name. Note that the importable package directory must use underscores where your project name uses hyphens:

```toml
[project]
name = "your-project-name"

[tool.hatch.build.targets.wheel]
packages = ["src/your_project_name"]
```

Rename the source directory to match:

```shell
mv src/python_template src/your_project_name
```

**2. Enable version bumping**

Version bumping is disabled in the template repo by default. To enable it for your new repository, go to:

*Settings → Secrets and variables → Actions → Variables → New repository variable*

Add a variable named `ENABLE_VERSION_BUMP` with the value `true`.

**3. Set branch protection (optional but recommended)**

If your repository is public, go to *Settings → Rules → Rulesets* and create a branch ruleset targeting `main` with the following rules enabled:

- Restrict deletions
- Require a pull request before merging (0 required approvals)
- Block force pushes
- Require status checks to pass — add `Lint`, `Security audit`, `Test / Python 3.12`, and `Test / Python 3.13`

**4. Allow GitHub Actions to create pull requests**

By default GitHub prevents Actions from opening pull requests. This is required for the automated version bump PR to work. Go to:

*Settings → Actions → General → Workflow permissions*

Enable **Allow GitHub Actions to create and approve pull requests**.

**5. Replace the placeholder test**

A placeholder test exists at `tests/test_placeholder.py` to keep CI green until real tests are written. Replace it with your own tests as you build out the project.

---

### Environment Setup

This project uses **uv** to manage dependencies.
To setup your environment run the following commands:

```shell
# Create virtual environment and install dependencies
uv sync

# Install all pre-commit hooks
uv run pre-commit install
```
