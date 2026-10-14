# DVWA-002: Stored Cross-Site Scripting

## Executive Summary

The vulnerable security level stores user-controlled content and later renders it without sufficient output encoding. Unlike reflected XSS, the unsafe content can affect each user who views the stored record.

## Lab Details

| Field | Value |
|---|---|
| Environment | Authorized DVWA lab |
| Security level | `[RECORD LEVEL]` |
| Severity | High |
| Status | Testing |

## Objective

Determine whether harmless browser content submitted through a DVWA form is stored and executed when the page is revisited.

## Harmless Demonstration

Use only a local visual proof that makes no network request and accesses no user data.

Example lab input:

```html
<script>alert('Stored DVWA lab')</script>
```

## Evidence

1. Capture the empty or normal form state.
2. Submit the harmless input using test data.
3. Reload or revisit the page.
4. Capture the resulting alert and stored entry.
5. Reset the DVWA database after collecting evidence.

## Root Cause

The application stores untrusted input and later inserts it into HTML without sufficient validation, sanitization, and output encoding.

## Impact

Stored XSS can repeatedly affect multiple users and may enable content manipulation, phishing, or unauthorized actions within user sessions.

## Remediation

- Encode output for the precise HTML context.
- Validate input and sanitize rich content with a proven library when HTML is required.
- Use a restrictive Content Security Policy as defense in depth.
- Protect session cookies with modern attributes.
- Review stored data and remove unsafe historical content.

## Retest

Confirm the same harmless input is rejected, sanitized, or rendered as inert text at a stronger security level.

`[ADD ACTUAL RETEST RESULT]`

