# Python Project Template

A modern Python project template with best practices and automated tooling.

## Features

- **UV**: Fast Python package installer and resolver
- **pytest**: Testing framework with coverage reporting
- **Ruff**: Lightning-fast Python linter and formatter
- **mypy**: Static type checking
- **pre-commit**: Git hooks for code quality
- **GitHub Actions**: Automated CI/CD pipeline with intelligent caching

## Prerequisites

- Python 3.10 or higher
- [UV](https://github.com/astral-sh/uv) package manager

## Installation

1. Install UV (if not already installed):
```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

2. Install project dependencies:
```bash
uv pip install -e ".[dev]"
```

3. Set up pre-commit hooks:
```bash
pre-commit install
```

## Project Structure

```
.
├── src/                    # Source code
├── tests/                  # Test files
├── .github/
│   └── workflows/
│       └── ci.yml         # GitHub Actions CI pipeline
├── .pre-commit-config.yaml # Pre-commit hooks configuration
├── pyproject.toml         # Project metadata and dependencies
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## Usage

### Running Tests

```bash
# Run all tests
pytest

# Run with coverage report
pytest --cov=src --cov-report=html

# Run specific test file
pytest tests/test_example.py
```

### Code Quality

```bash
# Run ruff linter
ruff check .

# Run ruff formatter
ruff format .

# Run type checking
mypy src

# Run all pre-commit hooks
pre-commit run --all-files
```

### Development

```bash
# Install package in development mode
uv pip install -e .

# Install with dev dependencies
uv pip install -e ".[dev]"

# Update dependencies
uv pip compile pyproject.toml -o requirements.txt
```

## CI/CD

The project includes a GitHub Actions workflow that:

- Runs on Python 3.10, 3.11, 3.12, and 3.13
- Caches UV packages, pre-commit hooks, Ruff, and mypy
- Executes pre-commit hooks
- Runs linting with Ruff
- Performs type checking with mypy
- Runs tests with pytest and generates coverage reports
- Uploads coverage to Codecov (optional)

## Configuration

### Ruff

Configuration in `pyproject.toml` under `[tool.ruff]`:
- Line length: 120
- Enabled: pycodestyle, pyflakes, isort, flake8-bugbear, and more

### mypy

Configuration in `pyproject.toml` under `[tool.mypy]`:
- Relaxed type checking for flexibility
- Python 3.10+ compatibility

### pytest

Configuration in `pyproject.toml` under `[tool.pytest.ini_options]`:
- Test discovery in `tests/` directory
- Coverage reporting enabled

## Contributing

1. Create a new branch for your feature
2. Make your changes
3. Ensure all tests pass and code quality checks succeed
4. Submit a pull request

## License

[Add your license here]

## Authors

[Add your name and contact information]
