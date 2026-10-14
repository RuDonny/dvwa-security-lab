# Evidence Checklist

Before publishing a case study:

## Technical Evidence

- [ ] State the objective and authorized scope
- [ ] Record the DVWA security level
- [ ] Capture normal behavior before testing
- [ ] Capture the harmless test input
- [ ] Capture the resulting application behavior
- [ ] Explain why the behavior proves the finding
- [ ] Identify likely impact
- [ ] Recommend specific remediation
- [ ] Document the retest result

## Sanitization

- [ ] Remove public and private IP addresses where unnecessary
- [ ] Remove usernames, email addresses, device names, and account identifiers
- [ ] Remove cookies, session IDs, CSRF tokens, passwords, and API keys
- [ ] Check browser tabs, bookmarks, notifications, and taskbar details
- [ ] Check terminal history and prompts
- [ ] Use test data only
- [ ] Confirm the repository contains no `.env` or credential files

## Recruiter Readability

- [ ] Explain the issue in plain language
- [ ] Separate evidence from assumptions
- [ ] Include business impact
- [ ] Include remediation and retest guidance
- [ ] Use captions that explain what each screenshot proves

