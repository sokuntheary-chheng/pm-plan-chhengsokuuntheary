# DR-01 · Open-day priority scope, week 10

**Date:** 2026-10-24 (week-4 role-play scenario)  
**Status:** Approved in simulation only; actual sponsor ratification is pending  
**Requested by:** Head of IT

## Context

The challenge scenario asks for every Should feature by W10 while retaining the W14 pilot. It is a separate role-play from the unresolved CR-03 W12 calendar case; this record does not change that case. For this role-play, W14 is fixed by the challenge prompt, while C-01 (W14 pilot baseline); the W12 CR-03 case stays separate. C-02 keeps all 8 Must features (300 h), C-03 caps cash at 200 USD, C-04 retains the 20-session × 100-participant single-server and ≤ 500 ms p95 targets, and C-05 retains S09's campus-data approval before the pilot.

After two sprints, 148 h of the 300 h Must total are complete; 152 h remain. The five Should features total 110 h. W5-W10 capacity is 6 × 40 = 240 h, so Must plus all Should requires 262 h and is short by 22 h (0.55 weeks), before preserving any of the 56 h contingency.

## Options considered

| Option | Time | Cost | Quality |
| ------ | ---- | ---- | ------- |
| 1 · Complete F16 (30 h) + F11 (24 h) by W10 | 0 weeks; 206 h total with remaining Must, 34 h capacity left | 0 USD | O3/O4/O5 remain required; other 56 h Should items finish by W14 |
| 2 · Build a mocked-analytics demo in 8 h | 0 weeks; 160 h total with remaining Must, 80 h capacity left | 0 USD | Data is labeled mock; F09/F11/F12/F13/F16 (110 h) stays for W14 |
| 3 · Complete all Should by W10 | +0.55 weeks, or use 22 h of the 56 h contingency | 0 USD | W10 deadline is missed if contingency is preserved; using it leaves 34 h |

## Decision

Approve option 1 for this role-play. Schedule F16 (30 h) and F11 (24 h) by W10; schedule F09 (20 h), F12 (12 h) and F13 (24 h) for the W14 pilot. Do not schedule Could work before W11. F17 (12 h) remains Won't; no new feature is classified Won't.

## Consequences

- Add an Open Day Demo milestone at W10; preserve the W14 pilot.
- Keep all feature estimates unchanged; the W10 demo uses 206 h of 240 h capacity, leaving 34 h.
- Add risk R-10: audience may mistake the unfinished W10 build for the full Should scope; state that F09, F12 and F13 are due at W14.
- No new Won't items; F17 remains the existing Won't item.
- Actual sponsor approval and confirmation of C-05 readiness are still required.

## Approvers

Head of IT (simulated sponsor) · Tal Tongsreng (simulated PM)
