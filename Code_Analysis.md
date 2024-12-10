------------------------------
**Part 1: Code Review**
------------------------------

We start this report by identifying common CWEs that affect software code and are of critical importance, these CWEs are as follows:

- CWE-20: Improper Input Validation
- CWE-116: Improper Encoding or Escaping of Output
- CWE-352: Cross-Site Request Forgery (CSRF)
- CWE-798: Use of Hardcoded Credentials
- CWE-285: Improper Authorization
- CWE-311: Missing Encryption of Sensitive Data
- CWE-89: SQL Injection
- CWE-79: Improper Neutralization of Input During Web Page Generation ('XSS')

We ran manual and automated tests. In the manual tests, we evaluated the following files that control essential functions of the software such as login, authorization and role assignments.

------------------------------
**Part 2: Key Findings and Contributions**
------------------------------
