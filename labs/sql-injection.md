# DVWA-003: SQL Injection

## Executive Summary

The vulnerable security level constructs a database query using untrusted input. In a real application, this could allow unauthorized access to data or modification of database operations.

## Lab Details

| Field | Value |
|---|---|
| Environment | Authorized DVWA lab |
| Security level | `[RECORD LEVEL]` |
| Severity | High |
| Status | Testing |

## Objective

Determine whether the application treats user input as part of a SQL command instead of as data.

## Safe Test Method

1. Submit a normal numeric identifier and record the expected result.
2. Submit a minimal lab-only boolean-condition test inside DVWA.
3. Compare the response with the baseline.
4. Do not target external systems, retrieve unnecessary data, or attempt persistence.

The exact evidence should be recorded in the report after the authorized DVWA test is performed.

## Evidence

- Baseline request and response
- Harmless altered request
- Difference in returned records or application behavior
- Sanitized DevTools or proxy capture

## Root Cause

Untrusted input is concatenated into a SQL statement rather than passed through a parameterized query.

## Impact

In a real application, SQL injection can expose sensitive information, bypass authorization, alter records, or damage application availability depending on database permissions.

## Remediation

- Use parameterized queries or prepared statements.
- Avoid dynamically constructing SQL with untrusted input.
- Apply server-side input validation.
- Use a least-privileged database account.
- Return generic error messages to users and keep detailed errors in protected logs.
- Add automated tests for injection-resistant behavior.

## Retest

At a stronger DVWA security level, repeat the same harmless test. The input should be treated strictly as data and should not alter query logic.

`[ADD ACTUAL RETEST RESULT]`

