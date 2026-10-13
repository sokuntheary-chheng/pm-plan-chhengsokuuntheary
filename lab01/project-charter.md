# Project charter: Realtime Quiz platform

| Field   | Value                            |
| ------- | -------------------------------- |
| Version | 1.0 (draft for sponsor approval) |
| Date    | 2026-09-29                       |
| Sponsor | Head of the IT department        |
| PM      | Tal Tongsreng, supervising lecturer |

## 1. Purpose and justification

Instructors currently spend about one hour per week each marking quiz answers by hand and give students no feedback while a quiz is running. This project builds the Realtime Quiz platform: a web application on which instructors author multiple-choice quizzes and host live timed sessions in which students join by code, answer against a timer, and see scores and a leaderboard update instantly over WebSocket. The department keeps student data on campus and avoids per-seat SaaS fees. The investment is justified with a numeric comparison of do-nothing, buy-SaaS and build options in business-case.md. The platform is demonstrated as an MVP in week 7 and piloted with 50 students in week 14.

## 2. Objectives and success criteria

| #   | Objective (what will be true) | Success criterion (number + week) |
| --- | ----------------------------- | --------------------------------- |
| O1  | All eight Must features of the MVP work in one live demo | 8 of 8 Must features accepted in the demo, week 7 |
| O2  | The platform runs a live pilot session with real users | 50 participants, 0 blocking defects, week 14 |
| O3  | Live broadcasts reach every connected client quickly enough for classroom use | ≤ 500 ms at the 95th percentile, measured week 13 and week 14 |
| O4  | One server instance handles the department's peak load | 20 concurrent sessions of 100 participants on 2 vCPU / 2 GB RAM, week 13 |
| O5  | The codebase is tested and merges stay green | ≥ 80 % line coverage, CI green on every merge, week 14 |

## 3. High-level scope

In scope:
- Quiz authoring with multiple-choice questions
- Live session engine with a server-authoritative timer per question
- Real-time scoring and leaderboard over WebSocket
- Authentication and role management for instructors and students
- Analytics and reporting dashboard
- Export of results to CSV and PDF

Out of scope:
- Native mobile applications
- Question types other than multiple choice
- Video conferencing
- LMS integration
- Multi-node scaling (single server instance only)

## 4. Milestones

| Week | Milestone                       | Ends process group |
| ---- | ------------------------------- | ------------------ |
| 1    | Charter approved, team formed   | Initiating         |
| 3    | Development environment, PM plan and CI pipeline ready | Planning |
| 5    | Accounts, security and quiz authoring complete | Executing |
| 7    | MVP demo                        | Executing          |
| 10   | Analytics and CSV/PDF export complete | Executing |
| 13   | Pilot readiness: load test at 100 simulated students green, runbook and data approval in place | Monitoring and controlling |
| 14   | Pilot with 50 students, closure | Closing            |

## 5. Budget summary

Effort:  students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h
Cash:    hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14 % of the 175 USD non-reserve cash lines)
         total 200 USD

## 6. Assumptions
- The campus proxy forwards WebSocket traffic, or the SockJS fallback keeps live updates usable.
- The four students and the supervising lecturer are available 8 h and 3 h per week respectively for all 14 weeks.
- The sponsor provides the Linode VPS at gicitc.com and the domain inside the 200 USD cap.
- Students are unpaid; the 10 USD per hour used in business-case.md is a notional rate for comparison only.

## 7. Constraints
- The project runs for 14 weeks only, from 2026-09-29, with the pilot fixed in week 14.
- Total cash spending is capped at 200 USD.
- Total effort is capped at 490 person-hours (448 student + 42 PM).
- The MVP demo is fixed in week 7 and must cover all Must features.
- The platform runs on a single server instance; multi-node scaling is excluded.
- Student names and results are stored on campus under the data protection officer's retention rule.

## 8. High-level risks
- The campus proxy may block WebSocket; the fallback is SockJS.
- Spring Boot 4 and Spring Security 7 are newer than most tutorials, so examples and help are scarce.
- Late answers may race with the closing of a question; the server's timer is authoritative to contain this.

## 9. Project manager authority

The PM re-plans work inside the 490 person-hours and the 200 USD cap without approval, including swapping tasks of equal size and adjusting the detailed schedule. Adding scope, moving the MVP demo or the pilot date, or spending beyond the 25 USD reserve needs the sponsor's written approval within 5 working days.

## 10. Approval

Sponsor: ____________________  Date: ________
PM:      ____________________  Date: ________
