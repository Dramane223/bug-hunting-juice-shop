# Bug Hunting on Open Bug Bounty Target (Practical Demonstration)

**Name:** Dramane Traore
**UID:** 24BCY70270

## Overview

This project demonstrates the practical application of bug hunting methodology on a deliberately vulnerable web application (OWASP Juice Shop), simulating the real-world process used on Open Bug Bounty targets. Testing was performed locally via Docker, following a full reconnaissance → scanning → manual testing → exploitation → reporting cycle.

## Findings Summary

| # | Vulnerability | Location | Severity |
|---|---|---|---|
| 1 | DOM-Based Cross-Site Scripting (XSS) | Product search field | Medium–High |
| 2 | SQL Injection (Authentication Bypass) | Login form | Critical |

- **XSS payload:** `<img src=x onerror=alert('XSS')>`
- **SQLi payload:** `' OR 1=1--`

An additional IDOR test on the basket API returned a negative result (endpoint correctly enforced JWT authentication).

## Contents

- `Cyber_Security_Major_Project_Report.docx` — full report with methodology, findings, impact analysis, and remediation recommendations
- `screenshots/` — proof-of-concept evidence for each vulnerability

## Environment

- Target: OWASP Juice Shop (`bkimminich/juice-shop`), run locally via Docker
- Access point: `http://localhost:3000`
- Testing approach: manual black-box testing

## Disclaimer

All testing was performed exclusively against a locally-hosted, intentionally vulnerable training application (OWASP Juice Shop). No external or production systems were tested.
