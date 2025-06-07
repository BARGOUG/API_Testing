# 🔐 API-Security-Testing – OWASP API Top 10 Based Assessment

## 📖 Introduction

This repository is dedicated to conducting comprehensive **API security testing** aligned with the **[OWASP API Security Top 10 (2023)](https://owasp.org/www-project-api-security/)**.  The goal is to identify and remediate common security risks in RESTful and GraphQL APIs by systematically evaluating them against the most critical threats defined by OWASP.

As modern applications increasingly rely on APIs for communication between services, ensuring their security has become crucial. This lab provides a structured approach to testing APIs for vulnerabilities such as broken authentication, insecure endpoints, insufficient logging, and more.

---

## 🎯 Objectives

- Evaluate APIs for compliance with the **OWASP API Security Top 10 (2023)**.
- Identify and document vulnerabilities using manual and automated techniques.


---

## 🔍 What’s Covered?

Each directory or test case in this repository corresponds to one or more entries from the **OWASP API Security Top 10**, including:

| OWASP API Top 10 ID | Vulnerability |
|---------------------|---------------|
| API1:2023           | Broken Object Level Authorization |
| API2:2023           | Broken Authentication |
| API3:2023           | Broken Object Property Level Authorization |
| API4:2023           | Unrestricted Resource Consumption |
| API5:2023           | Broken Function Level Authorization |
| API6:2023           | Untrusted Data Storage |
| API7:2023           | Improper Inventory Management |
| API8:2023           | Improper Rate Limiting |
| API9:2023           | Improper Logging & Monitoring |
| API10:2023          | Improper Error Handling |

---

## 🧰 Tools Used

- **Postman / Burp Suite – Manual API testing
- **ffuf / curl /  – Automation and fuzzing
- **Python scripts** – Custom checks and reporting
