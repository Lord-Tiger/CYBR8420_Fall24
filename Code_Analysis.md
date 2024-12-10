------------------------------
**Part 1: Code Review**
------------------------------
The software we are evaluating (OpenEMR) has different parts and our strategy was to perform a manual analysis on parts of the code such as login, authorization and Admin ACL as well as conducting an automated code analysis on the whole repository using different tools. We used AI to understand the code and to help analyze the code for best security practices. We start this report by identifying common CWEs that affect software code and are of critical importance, these CWEs are as follows:

- CWE-20: Improper Input Validation
- CWE-116: Improper Encoding or Escaping of Output
- CWE-352: Cross-Site Request Forgery (CSRF)
- CWE-798: Use of Hardcoded Credentials
- CWE-285: Improper Authorization
- CWE-311: Missing Encryption of Sensitive Data
- CWE-89: SQL Injection
- CWE-79: Improper Neutralization of Input During Web Page Generation ('XSS')

We ran manual and automated tests. In the manual tests, we evaluated the following files that control essential functions of the software such as login, authorization and role assignments.

- interface/login/login.php
- oauth2/authorize.php
- interface/usergroup/adminacl.php

**Manual Code Review**
CWE-89: SQL Injection

Issue:

The SQL queries use sqlStatement but do not clearly demonstrate parameterized queries. The following code taken from 63-64 of OpenEMRs login code shows a good security implementation. However, it is important to ensure all such queries are parameterized throughout the codebase.

    $sql = "SELECT option_id, title,is_default FROM list_options WHERE list_id=? and activity=1 ORDER BY seq, option_id";
    $rs = sqlStatement($sql, ['apps']);

Mitigation: Validate that all SQL queries across the platform use parameterized queries. Always sanitize input when constructing queries dynamically.

CWE-79: Improper Neutralization of Input During Web Page Generation ('XSS')

Issue:
On line 87-88 of the login code, User-provided input like $_REQUEST['app'] is being processed and used to generate HTML, which might lead to XSS if attr() and other sanitization functions are insufficient or not uniformly applied:
    
    $div_app = sprintf('', attr($_REQUEST['app']));

Mitigation: The developers must ensure all inputs are sanitized using robust methods like htmlspecialchars() or equivalent. Apply output encoding consistently when rendering HTML, especially for dynamic inputs.

CWE-285: Improper Authorization
    
Issue: Starting on line 32 of the authorization script of OpenEMR. Authorization checks ($imauthorized) depend on $_SESSION['userauthorized'] and $see_auth values, which might not fully reflect user roles or permissions.
Example: 

    $see_auth > 2 might grant excessive privileges.
    
Mitigation: Implement stricter role-based access control (RBAC). Validate session values like $_SESSION['userauthorized'] rigorously.

CWE-352: Cross-Site Request Forgery (CSRF)

**Issue:** CSRF protection is implemented via CsrfUtils::verifyCsrfToken(), but not consistently:

Only the authorize action ($_GET["mode"] == "authorize") checks the CSRF token. Other actions and AJAX calls do not validate CSRF tokens.

Mitigation: Enforce CSRF validation on all state-changing requests.
Use secure and hidden CSRF tokens consistently

------------------------------
**Part 2: Key Findings and Contributions**
------------------------------
