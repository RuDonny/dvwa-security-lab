# DVWA-001: Reflected Cross-Site Scripting

## Executive Summary

The application returns user-controlled input to the page without sufficient context-aware output encoding at the vulnerable security level. In a real application, an attacker could potentially craft a link that causes script execution in another user's browser.

## Lab Details

| Field | Value |
|---|---|
| Environment | Authorized DVWA lab |
| Security level | `[RECORD LEVEL]` |
| Severity | Medium |
| Status | Testing |

## Objective

Determine whether harmless user input is interpreted as executable browser content when reflected in the response.

## Harmless Demonstration

Use a simple visual proof such as a lab-only alert containing no external connection, credential access, persistence, or obfuscation.

Example lab input:

```html
<script>alert('DVWA lab')</script>
```

## Evidence

1. Capture the normal page response using plain text.
2. Submit the harmless lab input.
3. Capture the resulting test alert.
4. Use DevTools to identify where the input appears in the response.

Add sanitized screenshots under `screenshots/` and link them here.

## Root Cause

Untrusted input is inserted into HTML without appropriate context-aware output encoding.

## Impact

In a real application, reflected XSS could support phishing, page-content modification, or actions performed in the context of a victim's authenticated session.

## Remediation

- Apply context-aware output encoding.
- Validate input using allowlists where practical.
- Use templating frameworks that escape output by default.
- Deploy a restrictive Content Security Policy as defense in depth.
- Mark session cookies `HttpOnly`, `Secure`, and with an appropriate `SameSite` value.

## Retest

Repeat the same harmless input at a stronger DVWA security level. The expected result is that the input is encoded, rejected, or displayed only as text.

`[ADD ACTUAL RETEST RESULT]`

