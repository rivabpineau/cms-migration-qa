# AGENTS Instructions for cms-migration-qa

This repository contains scripts and configuration for automating a large-scale
content migration from a legacy CMS to a new platform, as well as utilities for
performing quality assurance (QA) on the migrated content. Contributors and
automation agents should adhere to the following guidelines.

## General Guidelines
- Use **Python 3.11** for all code in this repository.
- Follow PEP8 style conventions and include type hints for new Python code.
- Document public functions and modules with docstrings.
- Keep functions small and focused; prefer composition over complex monoliths.
- Commit messages should be concise and in the imperative mood, e.g., `Add QA
  script for image links`.

## Repository Structure
- `migration/` – scripts and utilities for exporting data from the legacy CMS
  and importing it into the new platform.
- `qa/` – validation tools to verify data integrity and content quality.
- `tests/` – automated tests.
- `docs/` – developer and operator documentation.

Not all directories may exist yet, but new code should conform to this layout.

## Setup
1. Create a Python virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Programmatic Checks
Before opening a pull request, run the following commands from the repository
root and ensure they complete without errors:

```bash
pytest
flake8
```

If these tools are missing, add them to `requirements.txt` and configure a basic
`setup.cfg` or `pyproject.toml` for lint settings.

## Pull Request Expectations
- Summarize the reason for the change.
- Include a list of commands or scripts that reviewers can run to reproduce the
  behavior or test results.
- Reference related issues when applicable.

## Notes for Automation
- Do not attempt large-scale network operations or destructive migration steps
  unless operating in a clearly defined staging environment.
- Use environment variables or config files to specify credentials; never commit
  sensitive data.

