# Business case: live quizzes for the IT department

## 1. Problem

Ten lecturers in the IT department run multiple-choice quizzes and mark the answers by hand. Each lecturer spends about one hour per week marking quiz answers, and students get no feedback while the quiz is running. Over a 30-week teaching year that is roughly 300 person-hours of marking, worth 3,000 USD at the notional student rate, plus the opportunity cost of no live feedback. Assumptions:

- lecturers running quizzes: 10
- marking time per lecturer per week: 1 h
- teaching weeks per year: 30
- notional value of one hour: 10 USD (students are unpaid; used to compare)
- SaaS price: 15 USD per lecturer per month — **assumption**; no education-pricing page was cited, so the chapter's fallback price is used throughout

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
| ------ | ----------- | ------------ | ----------- | -------------- |
| A      | Do nothing: keep marking by hand, no live quizzes | 0            | 0           | 0              |
| B      | Buy a Kahoot-like quiz SaaS at the assumed 15 USD per lecturer per month | 0            | 1,800       | 3,000          |
| C      | Build Realtime Quiz with the charter budget (490 h effort, 200 USD cash) | 4,900        | 300         | 4,800          |

Cost and benefit periods: option C's one-off 4,900 USD is the charter effort (490 person-hours at the notional 10 USD/h); its annual cost is one year of operation at 12 × 25 = 300 USD hosting. The charter's cash line of 4 × 25 = 100 USD covers hosting only for the 14-week project period inside the 200 USD cap — it is not the annual operating cost. Option C's annual benefit counts both the 3,000 USD marking time saved and the 1,800 USD SaaS fee avoided (it removes the need for option B).

## 3. Comparison

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
| ------ | ------------------ | --------------- | -------------------------- |
| B      | 3,000 − 1,800 = 1,200 | 0 (no one-off cost) | 1,800 − 1,080 = 720 |
| C      | 3,000 + 1,800 − 300 = 4,500 | 4,900 / 4,500 ≈ 1.1 | 1,800 + 1,080 − 300 = 2,580 → 4,900 / 2,580 ≈ 1.9 |

Sensitivity: with 6 lecturers every lecturer-dependent line is scaled — marking time saved falls from 3,000 to 1,800 USD per year, the SaaS fee (and the fee avoided by building) falls from 1,800 to 1,080 USD per year, and hosting stays at 300 USD; the one-off build effort stays at 4,900 USD. Option C still pays back inside two academic years.

## 4. Benefits not priced

- Learning outcome: the capstone is a real product the four students can show to employers.
- Data ownership: student names and results stay on campus under the data protection officer's retention rule.
- No per-seat limit: after go-live the department can add lecturers without paying per seat.

## 5. Risks per option

- **A (do nothing):** the weekly marking load continues and grows with enrolment; students keep getting no live feedback; the department falls behind on the innovation the sponsor wants to show.
- **B (buy SaaS):** the per-seat bill grows with adoption (10 lecturers today, more next semester); live sessions depend on the vendor's availability outside campus control; student data leaves campus, which makes the data protection officer's approval harder; renewal prices can rise.
- **C (build):** the campus proxy may block WebSocket (fallback SockJS); Spring Boot 4 and Spring Security 7 are newer than most tutorials; late answers may race with the closing of a question; client clocks drift from the server; PDF export must render Khmer names; Could features may creep into the MVP.

## 6. Recommendation and review gate

Recommendation: **option C, build Realtime Quiz**. It pays back in about 1.1 years at 10 lecturers and still about 1.9 years at 6 lecturers, and the department keeps its data and the capstone learning outcome. Review gate: if the **MVP demo in week 7** fails, the sponsor buys option B for the next semester and treats the build as a two-semester project.
