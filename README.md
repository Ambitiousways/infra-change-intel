
# Infrastructure Change Intelligence Platform

A production-style system for analyzing infrastructure configuration changes, assessing risk impact, and generating role-based summaries for engineering, security, and leadership audiences.

This project demonstrates how real-world infrastructure changes can be reviewed, understood, and documented without manual diffing or guesswork.

---

## Why This Project Exists

Infrastructure changes are a leading cause of outages, security incidents, and audit findings.
Yet many teams rely on informal reviews, screenshots, or tribal knowledge to understand what changed.

This platform provides:

* **Clear visibility** into what changed
* **Risk-aware analysis** of those changes
* **Audience-appropriate summaries** that support decision-making
* **Persistent history** for audits and retrospectives

It is designed for enterprise and regulated environments where reliability, traceability, and security matter.

---

## Key Features

* **Change Diff Engine**

  * Compares nested “before” and “after” infrastructure states
  * Identifies added, removed, and modified configuration elements

* **Risk Scoring**

  * Rules-based assessment of security and operational impact
  * Flags high-risk exposure such as legacy services or disabled controls

* **Role-Based Summaries**

  * **Engineer:** Detailed configuration changes
  * **Security:** Risk triggers and impact context
  * **Executive:** Concise, decision-ready overview

* **Multiple Interfaces**

  * REST API (FastAPI + OpenAPI)
  * Command-line interface (Typer)
  * Shared core logic across API and CLI

* **Persistence**

  * Stores analysis history using SQLite (SQLAlchemy)
  * Enables audits, comparisons, and trend analysis

* **Automated Testing**

  * Unit and API tests using pytest
  * Continuous Integration via GitHub Actions

---

## Example Use Cases

* Infrastructure change reviews
* Security impact assessments
* Pre-deployment validation
* Post-incident analysis
* Audit and compliance documentation
* Change advisory board (CAB) support

---

## How This Would Be Used in Production

In a production environment, this platform would be run as an **authorized assessment tool** to validate configuration changes before or after deployment.

Typical workflows include:

* Comparing planned vs actual system states
* Verifying that security baselines were not violated
* Identifying unintended exposure caused by changes
* Providing documented evidence for audits or reviews

The system is intentionally **non-intrusive**, focusing on visibility and analysis rather than exploitation.

---

## API Usage

Start the API locally:

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python -m uvicorn api.main:app --reload
```

Open API documentation:

```
http://127.0.0.1:8000/docs
```

Available endpoints:

* `POST /analyze`
* `POST /analyze-from-files`
* `GET /history`
* `GET /analysis/{id}`

---

## CLI Usage

Analyze two configuration files:

```bash
python -m cli.main analyze-files data/example_before.json data/example_after.json
```

Analyze without saving to the database:

```bash
python -m cli.main analyze-files data/example_before.json data/example_after.json --no-save
```

View history:

```bash
python -m cli.main history
```

---

## Testing

Run the full test suite:

```bash
pytest -q
```

Tests cover:

* Change diff logic
* Risk scoring rules
* Summary generation
* API endpoints

---

## Why This Stands Out

This project goes beyond a simple demo by showing:

* Clean project structure
* Separation of concerns
* Shared business logic across interfaces
* Persistence and audit readiness
* Automated testing and CI
* Realistic enterprise use cases

It reflects how infrastructure and security tooling is built and maintained in professional environments.

---

## Roadmap

* Authentication and role-based access
* PDF report generation
* Integration with ticketing/change systems
* Historical drift visualization
* Policy-driven risk rules




