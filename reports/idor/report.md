# IDOR Vulnerability Assessment

## Executive Summary

This report demonstrates several scenarios of
Insecure Direct Object Reference (IDOR)
vulnerabilities.

## Vulnerability Overview

### What is IDOR?

This vulnerability allows unauthorized access to user accounts, downloading other users' files, and reading other users' data.

### Impact

- Unauthorized Access
- Data Disclosure
- Privilege Escalation

## Case Study #1

### Title
Privilege Escalation

### Description
The user can change the status of the request and change their account status from a regular user to a user with admin privileges.

### Evidence

GET /my-account?id=wiener

Cookie: session=SESSION-TEXT; Admin=false

change cookies to :

Cookie: session=SESSION-TEXT; Admin=true

### Result 

Privilege Escalation from normal user to adminitration role.

### Risk

High

### Remediation

Implement server-side authorization checks.

## Conclusion

The tested scenarios demonstrate that IDOR vulnerabilities are primarily authorization issues rather than authentication issues.

Applications should never rely on client-supplied identifiers without validating ownership and permissions on the server side.

Proper authorization controls significantly reduce the risk of unauthorized access and privilege escalation.
