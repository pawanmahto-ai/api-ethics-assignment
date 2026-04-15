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
import time
import os
API_KEY = os.getenv("API_KEY")

### Issue 2: No Rate Limiting
Problem: Too many requests can overload API

Fix:
python
import time

for page in range(1, 101):
    response = requests.get(API_URL, params={"page": page, "key": API_KEY})
    data = response.json()
    records.extend(data["results"])
    time.sleep(1)
