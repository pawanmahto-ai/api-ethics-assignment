# API Ethics Assignment

## Task 1 — Classify and Handle PII Fields

| Field            | Type        | Action          | Reason |
|------------------|------------|----------------|--------|
| full_name        | Direct PII | Drop           | Directly identifies a person |
| email            | Direct PII | Mask           | Sensitive but useful |
| date_of_birth    | Indirect PII | Generalize   | Can identify indirectly |
| zip_code         | Indirect PII | Generalize   | Location info |
| job_title        | Non-PII     | Keep          | Not sensitive |
| diagnosis_notes  | Sensitive Data | Pseudonymize | Health data |

## Task 2 — Ethical Issues

### Issue 1: Hardcoded API Key
Problem: Security risk

Fix:
```python
import os
API_KEY = os.getenv("API_KEY")
