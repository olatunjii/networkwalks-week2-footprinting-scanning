# theHarvester Task 2 – Sanitized Results Summary

Command: `theHarvester -d microsoft.com -l 50 -b all` (run 9 Nov 2026, theHarvester 4.10.1)

| Item | Count / value |
|------|---------------|
| Hosts | 9,967 (not republished) |
| IPs | 55 (not republished) |
| ASNs | 8: AS8075, AS13335, AS16509, AS16625, AS20940, AS40034, AS133618, AS206834 |
| Interesting URLs | 7 (public Microsoft pages and a sign-in redirect) |
| Emails | 3 role/bot addresses: `d***@`, `o***@`, `secure@microsoft.com` (published security contact) |
| People / LinkedIn | None |

**Hostname patterns (keyword matches overlap):** several hundred names contain pre-production markers such as `ppe`, `int`, `dev`, `uat`, `canary`; 21 are wildcard entries.

**Hudson Rock (aggregate, unverified):** 621,624 compromised records – 16,598 employee and 600,241 user. No emails or credentials were returned or viewed.

**Coverage limits:** 32 sources failed because of missing API keys; Fofa and LeakIX rejected invalid keys.

The full host list is deliberately not published because it describes a third party's infrastructure.
