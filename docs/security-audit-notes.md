# Security Audit Notes — npm Critical Advisories

Quarterly security sweep covering the current critical-severity advisories in the npm ecosystem. This document summarizes the three advisories tracked in this sweep. Tracking issue: #1.

| GHSA id | CVE id | Package | Severity | CVSS score | Earliest patched version |
| --- | --- | --- | --- | --- | --- |
| GHSA-673q-mjm6-r5xr | — | next | Critical | CVSS:4.0/AV:N/AC:L/AT:P/PR:N/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:N (no numeric score published) | 16.4.1 |
| GHSA-cg2g-xh64-v4q7 | — | dompurify | Critical | CVSS:4.0/AV:N/AC:L/AT:P/PR:N/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:N (no numeric score published) | 3.4.17 |
| GHSA-f2ph-cmg5-wxc8 | CVE-2026-114125 | storybook | Critical | No CVSS score published | 8.6.19 |

## 1. GHSA-673q-mjm6-r5xr — next

- **Package:** `next` (npm)
- **Severity:** Critical
- **CVSS score:** CVSS:4.0/AV:N/AC:L/AT:P/PR:N/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:N — no numeric CVSS score is published on the advisory; the CVSS v4 vector is recorded with an empty score object in the GitHub advisory API.
- **CVE id:** None listed on the advisory record (identifiers contain only the GHSA id).
- **Earliest patched version:** 16.4.1 (vulnerable range: >= 16.0.0, <= 16.4.0)
- **Summary:** Unauthenticated remote code execution in `use cache` functions returning typed arrays. Applications using the App router with Cache Component can be driven to remote code execution when a `use cache` function returns multiple typed arrays. There is no known workaround — upgrade immediately even if your application does not have similar functions.
- **Advisory link:** https://github.com/advisories/GHSA-673q-mjm6-r5xr
- **Sub-issue:** #2

## 2. GHSA-cg2g-xh64-v4q7 — dompurify

- **Package:** `dompurify` (npm)
- **Severity:** Critical
- **CVSS score:** CVSS:4.0/AV:N/AC:L/AT:P/PR:N/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:N — no numeric CVSS score is published on the advisory; the CVSS v4 vector is recorded with an empty score object in the GitHub advisory API.
- **CVE id:** None listed on the advisory record (identifiers contain only the GHSA id; no CVE alias present).
- **Earliest patched version:** 3.4.17 — DOMPurify 3.4.17 release notes: "Fixed an issue with `IN_PLACE`, `SAFE_FOR_TEMPLATES` and shadow roots".
- **Summary:** DOMPurify `SAFE_FOR_TEMPLATES` bypass — split template expressions survive in attached shadow root content on DOM output modes. With `SAFE_FOR_TEMPLATES: true` combined with a DOM-returning mode (`RETURN_DOM`, `RETURN_DOM_FRAGMENT`, or `IN_PLACE`), template expressions such as `{{...}}`, `${...}`, and `<%...%>` survive sanitization inside the text content of an attached shadow root, because the post-walk safety net never recurses into shadow roots. Feeding the sanitized output to a template engine yields XSS or template injection.
- **Advisory link:** https://github.com/advisories/GHSA-cg2g-xh64-v4q7
- **Sub-issue:** #3

## 3. GHSA-f2ph-cmg5-wxc8 — storybook

- **Package:** `storybook` (npm)
- **Severity:** Critical
- **CVSS score:** No CVSS score is published on the advisory record (the `cvss` object is empty in the GitHub advisory API; no numeric score or vector).
- **CVE id:** CVE-2026-114125
- **Earliest patched version:** 8.6.19 (for the >= 8.0.0, < 8.6.19 range; other patched majors: 9.1.21, 10.6.2, 11.0.0-alpha.6)
- **Summary:** Missing origin validation in the Storybook preview allows code injection from malicious websites. A malicious website may be able to cause unauthorized file changes in a developer's project while an affected Storybook dev server is running; under additional conditions, a changed file could be executed by a local runtime with the developer's privileges. Not known to be exploited in the wild.
- **Advisory link:** https://github.com/advisories/GHSA-f2ph-cmg5-wxc8
- **Sub-issue:** #4

---

Tracking issue: #1 — Security audit: npm critical advisories.
