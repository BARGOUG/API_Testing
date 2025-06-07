# Broken User Authentication Challenge

## Overview

This repository contains resources and solutions for the "Broken User Authentication" challenge from crAPI. The goal is to reset the password of a different user by exploiting vulnerabilities in the authentication mechanism.

---

## Challenge Details

### Challenge 3 - Reset the password of a different user

- **Objective**: Find an email address of another user on crAPI and reset their password.
- **Approach**:
  - **Find an email address**: Identify the email address of another user. This might involve enumerating users or using other vulnerabilities.
  - **Brute forcing**: If protection mechanisms are in place (e.g., rate limiting), consider leveraging the predictable nature of REST APIs to find more similar API endpoints.

For this demo we created two seperate accounts 'hamza' & 'yessine'

