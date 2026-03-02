# Environment Setup

## Prerequisites

- Python 3.10
- `virtualenv` (already available system-wide — no sudo required)

## Reproduce the Environment

```bash
# 1. Create the virtual environment
virtualenv .venv

# 2. Activate it
source .venv/bin/activate        # Linux / macOS
# .venv\Scripts\activate         # Windows

# 3. Upgrade pip
pip install --upgrade pip

# 4. Install all dependencies (exact versions, fully reproducible)
pip install -r requirements.lock

# Alternatively, install only top-level packages (lets pip resolve deps):
# pip install -r requirements.txt
```

## Verify

```bash
python -c "import torch, transformers, sklearn, pandas; print('OK')"
```

## Deactivate when done

```bash
deactivate
```

## Notes

- The `.venv/` directory is not committed to git (add it to `.gitignore`).
- To export the exact pinned versions at any point:
  ```bash
  pip freeze > requirements.txt
  ```
