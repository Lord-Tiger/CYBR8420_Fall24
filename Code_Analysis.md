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

Lack of experience in the PHP and JavaScript programming languages, at least to the level where we would be able to look at code and identify issues with the code quality beside basic intermediate things like hard coded credentials and lack of encryption on critical strings was a challenge, we overcame this challenge through research and the use of AI. AI was able to explain coding lines. The software itself was also well-documented, most scripts we looked at had comments and good descriptions of each script and its functions.

--------------------------------
**Manual Code Review**
--------------------------------

**Evaluating "interface/login/login.php"**
-------------------------------------

**CWE-89: SQL Injection**

**Issue:**

The SQL queries use sqlStatement but do not clearly demonstrate parameterized queries. The following code taken from 63-64 of OpenEMRs login code shows a good security implementation. However, it is important to ensure all such queries are parameterized throughout the codebase.

    $sql = "SELECT option_id, title,is_default FROM list_options WHERE list_id=? and activity=1 ORDER BY seq, option_id";
    $rs = sqlStatement($sql, ['apps']);

**Mitigation:** Validate that all SQL queries across the platform use parameterized queries. Always sanitize input when constructing queries dynamically.

**CWE-79: Improper Neutralization of Input During Web Page Generation ('XSS')**

**Issue:**
On line 87-88 of the login code, User-provided input like $_REQUEST['app'] is being processed and used to generate HTML, which might lead to XSS if attr() and other sanitization functions are insufficient or not uniformly applied:
    
    $div_app = sprintf('', attr($_REQUEST['app']));

**Mitigation:** The developers must ensure all inputs are sanitized using robust methods like htmlspecialchars() or equivalent. Apply output encoding consistently when rendering HTML, especially for dynamic inputs.

**CWE-285: Improper Authorization**
    
**Issue:**  

Starting on line 32 of the authorization script of OpenEMR. Authorization checks ($imauthorized) depend on $_SESSION['userauthorized'] and $see_auth values, which might not fully reflect user roles or permissions.
Example: 

    $see_auth > 2 might grant excessive privileges.
    
**Mitigation:** Implement stricter role-based access control (RBAC). Validate session values like $_SESSION['userauthorized'] rigorously.

**Evaluating "oauth2/authorize.php"**
-------------------------------------

**CWE-352: Cross-Site Request Forgery (CSRF)**

**Issue:** 
CSRF protection is implemented via the "CsrfUtils::verifyCsrfToken()" function, but not consistently across the board:

Only the authorization action ($_GET["mode"] == "authorize") checks the CSRF token. Other actions and AJAX calls in the script do not validate CSRF tokens.

**Mitigation:** Enforce CSRF validation on all state-changing requests.
Use secure and hidden CSRF tokens consistently

**CWE-20: Improper Input Validation**

**Issue:**

A potential issue with $_GET['site'] directly being assigned a global variable value without additional validation.

**Mitigation: Sanitize all inputs properly, including $gbl::$SITE and any other request parameters.

**CWE-116: Improper Encoding or Escaping of Output**

**Issue:**

The code does not explicitly ensure that all outputs (e.g., in error messages) are encoded or escaped, which might lead to issues like reflected XSS if values are rendered in a response.

**CWE-285: Improper Authorization**

**Issue:**

Access control seems to rely on conditions like $ignoreAuth = true or $gbl::$SITE checks. However, if these checks are improperly implemented or bypassed, it could allow unauthorized access to sensitive endpoints.
**CWE-311: Missing Encryption of Sensitive Data**

Issue:**

The SessionUtil::oauthSessionStart and SessionUtil::oauthSessionCookieDestroy methods are invoked.

**Mitigation:** Session cookies are marked “HttpOnly” and “Secure”, sessions should be invalidated upon logout or token expiration. Ensuring encryption is used wherever sensitive data is processed, especially for session cookies and CSRF tokens.


--------------------------------
**Automated Code Review**
--------------------------------
For the automated tests we conducted on OpenEMR, we chose two tools, SonarQube cloud and CodeQL which is offered by GitHub, both of our choices were influenced by the fact that both offer robust scanning capabilities directly on GitHub repositories. We forked the official OpenEMR repository and ran our scans on it using both tools. SonarQube helped us scanning the entire code from a PHP perspective since it’s the main language that the software uses, while CodeQL helped evaluate the JavaScript code which accounts to only about 4.9% of our code yet still a vital part that handles functions users interact with as shown below.

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/02c50dce979315008fa2cc2b3f10d7418c9636eb/Media/SonarQube11.png)

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/02c50dce979315008fa2cc2b3f10d7418c9636eb/Media/CodeQL.png)

SonarQube calculated a passing quality grade for the OpenEMR code as it stands with its latest version, still highlighted about 79 open security issues. Most of the issues appeared to flag issues with test files that the developers included for various tests. For instance, it flagged this script that is intended for de-identifying an OpenEMR database for the purpose of creating a live demo or for development using real data while keeping patient identities a secret by generating random data making this a false alarm.

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/5dfe99cf7ee7eb59f15d060cab87e70d6fac01ea/Media/SonarQube2.png)

On the flip side, it identified an issue with the code that would allow a user to craft an HTTP request with malicious content. This issue appears to have been introduced to the code years ago, it’s not been tested whether this is indeed exploitable, however.

![image](https://github.com/Lord-Tiger/CYBR8420_Fall24/blob/5dfe99cf7ee7eb59f15d060cab87e70d6fac01ea/Media/SonarQube3.png)

[SonarQube Report](https://sonarcloud.io/summary/new_code?id=Lord-Tiger_CYBR8420_Fall24-openemr&branch=master)

[Our Forked OpenEMR Repository](https://github.com/Lord-Tiger/CYBR8420_Fall24-openemr)

------------------------------
**Part 2: Key Findings and Contributions**
------------------------------

**Team Reflection:**

For this project, our group faced more challenges than usual since none of us have a background in coding. After meeting with the professor, we received valuable guidance on how to approach the task. Our objective was to scan the entire repository, map it to relevant CWE categories, and reflect on our findings. Initially, we struggled with dividing responsibilities among team members.

To tackle this, we relied on AI and referred to our previously submitted assignments. One team member conducted the static code analysis with the assistance of AI, while the automated analysis was performed by forking the repository into our GitHub and running a scan using SonarCloud. Given our limited coding expertise, AI proved to be an invaluable tool throughout the process.

The most significant challenge we faced was mapping our findings to the appropriate CWE categories, particularly with the list we had compiled. Aside from this, we did not uncover many issues, as it seems the developers had addressed most vulnerabilities prior to production—at least, that was our assumption based on the results.
