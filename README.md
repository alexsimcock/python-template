# Python Template

## Getting Started

### Repo Setup

After creating a new repository from this template, complete the following steps before writing any code.

**1. Configure project metadata and package name**

Update `pyproject.toml` with your project details, replacing all `python-template` placeholder references with your actual project name.

*Note: While project names typically use hyphens (e.g., `my-project`), Python import directories inside `src/` must use underscores (e.g., `my_project`):*

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

**2. Configure GitHub Pull Request & Merge settings**

Go to **Settings → General → Pull Requests**:
- [x] **Allow squash merging**
    - Set default message to: **Pull request title** (or *Pull request title and description*)
- [x] **Allow auto-merge** (Required for Dependabot automated dependency updates)

**3. Configure Workflow Permissions**

Go to **Settings → Actions → General → Workflow** permissions:

- Select **Read and write permissions** (*Required for `release-please` and Dependabot actions*)
- [x] **Allow GitHub Actions to create and approve pull requests**

**4. Set branch protection (optional but recommended)**

If your repository is public, go to **Settings → Rules → Rulesets** and create a branch ruleset targeting `main` with the following rules:

- Restrict deletions
- Block force pushes
- Require a pull request before merging (0 required approvals)
- Require status checks to pass — add:
    - `Pre-commit`
    - `Security audit`
    - `Validate PR Title`
    - `Test / Python 3.12`
    - `Test / Python 3.13`

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
uv run prek install
```
