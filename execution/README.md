# Execution Scripts (Layer 3 - The Hands)

This folder contains **reliable Python scripts** that perform API calls and data processing.

## Purpose

- Execute deterministic, tested operations
- Interface with external APIs (Turo, Gmail, Google Sheets, etc.)
- Process and transform data reliably

## Guidelines

1. **Single Responsibility**: Each script handles one specific task
2. **Error Handling**: Always include try/except with meaningful error messages
3. **Logging**: Use Python's logging module for traceability
4. **Configuration**: Read API keys from `.env` (never hardcode secrets)
5. **Testing**: Include unit tests for critical logic

## Naming Convention

`{domain}_{action}.py` — e.g., `turo_fetch_reservations.py`, `gmail_parse_emails.py`

## Standard Template

```python
"""
Script: {name}
Purpose: {description}
Directive: {link to directive}
"""
import os
import logging
from dotenv import load_dotenv

load_dotenv()
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

def main():
    # Implementation here
    pass

if __name__ == "__main__":
    main()
```
