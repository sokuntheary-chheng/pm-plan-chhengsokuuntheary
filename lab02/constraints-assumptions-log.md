# Constraints and assumptions log · Realtime Quiz · v0.1

| Id | Type | Statement (measurable) | Source / owner | Validate by |
| -- | ---- | ---------------------- | -------------- | ----------- |
| C-01 | Constraint | Pilot in week 14 with 50 students; 14 weeks x 40 h = 560 h | Charter, section 7 | fixed |
| C-02 | Constraint | All 8 Must features (300 h) remain in the pilot scope; Should and Could scope may be deferred. | Charter, section 2, O1; `features.csv` and `moscow.md` | fixed |
| C-03 | Constraint | Total project cash spending does not exceed 200 USD. | Charter, section 7, Budget | fixed |
| C-04 | Constraint | One 2 vCPU / 2 GB RAM server must support 20 concurrent sessions of 100 participants; broadcasts must be ≤ 500 ms at p95. | Charter, section 2, O3-O4 | before W14 pilot |
| C-05 | Constraint | Student names and results stay on campus; S09 approval is required before the W14 pilot. | Charter, section 7; `lab01/stakeholders.md`, S09 | W13, before W14 pilot |
| A-01 | Assumption | On the campus network, WebSocket or the SockJS fallback delivers broadcasts at ≤ 500 ms p95 in an end-to-end test. | Owner: PM and team | W7 → R-01 |
| A-02 | Assumption | The sponsor provides the Linode VPS at gicitc.com and the domain within the 200 USD cash cap. | Owner: Head of IT | W3 → R-02 |
| A-03 | Assumption | If the sponsor approves CR-03's W12 pilot proposal, S09 can complete student-data approval before W12 rather than at the current W13 readiness item. | Owner: Data protection officer | W10 → R-03 |
| A-04 | Assumption | The instructor can confirm 50 pilot participants for W14, or for W12 if the sponsor approves CR-03. | Owner: Instructor | W10 → R-04 |
| A-05 | Assumption | F11's 24 h CSV export includes the results needed to prepare a spreadsheet summary if F10 analytics is deferred. | Owner: PM | W10 → R-05 |
| A-06 | Assumption | The W10 open-day demo can use clearly labeled mocked analytics, built in 8 h without presenting mock results as live pilot data. | Owner: PM | W9 → R-10 |

Review at every milestone. Overdue assumption = open issue.

CR-03 proposes W12 (480 h); W12 and 480 h become the baseline only if the sponsor approves it. Until then, the baseline remains W14 and 560 h under C-01.
