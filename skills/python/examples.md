# Python Examples

These are adaptable patterns, not requirements to replace the project's existing conventions.

## Create a Virtual Environment

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

On macOS or Linux, activate with `source .venv/bin/activate`.

## Read a UTF-8 File Safely

```python
from pathlib import Path

def read_text(path: Path) -> str:
    return path.read_text(encoding="utf-8")
```

## Read Configuration from the Environment

```python
import os

api_key = os.getenv("SERVICE_API_KEY")
if not api_key:
    raise RuntimeError("SERVICE_API_KEY must be configured")
```

Do not include the key in logs, exceptions, notebooks, or source control.

## Test a Small Function with pytest

```python
def normalize_name(value: str) -> str:
    return " ".join(value.split()).casefold()

def test_normalize_name_collapses_whitespace():
    assert normalize_name("  Ada   Lovelace ") == "ada lovelace"
```

Run with `python -m pytest` when pytest is installed in the active environment.