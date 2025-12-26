\# Infrastructure Change Intelligence Platform



A FastAPI-based service that analyzes infrastructure configuration changes (before/after), assigns a risk rating, and generates role-based summaries for engineering, security, and executive audiences.



\## Why this project exists

Infrastructure changes are a common source of outages and security incidents. This service helps teams quickly understand what changed, why it matters, and what risk was introduced—without requiring manual diffing or long change review meetings.



\## Key features

\- Change diff engine for nested configuration objects

\- Rules-based risk scoring (extensible)

\- Role-based summaries:

&nbsp; - Engineer: detailed diff highlights

&nbsp; - Security: risk triggers and impact language

&nbsp; - Executive: concise, decision-ready summary

\- OpenAPI/Swagger documentation via `/docs`



\## Example output (local run)

\### API Docs Overview

!\[Docs Overview](./examples/screenshots/docs\_overview.png)



\### Analysis Response

!\[Docs Response](./examples/screenshots/docs\_response.png)



\### Server Run

!\[Terminal Run](./examples/screenshots/terminal\_run.png)



\## Run locally

```bash

python -m venv .venv

\# Windows:

.venv\\Scripts\\activate



pip install -r requirements.txt

python -m uvicorn api.main:app --reload

### Test Suite
This project includes unit and API tests to ensure consistent behavior as features evolve.

![Tests Passing](./examples/screenshots/tests_passing.png)


