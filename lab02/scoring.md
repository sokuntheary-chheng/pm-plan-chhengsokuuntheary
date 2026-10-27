# Weighted option scoring · Realtime Quiz

## Options

- **Build:** deliver the Software Engineering capstone as planned, using the team and 504 h planned-work baseline.
- **Buy:** use Kahoot! for live quizzes. The official school plans page lists a $9 monthly price and a 50-participant limit; four months cost $36, or 18 % of the 200 USD cash budget. The subscription price and participant limit were checked on 2026-10-27 at [Kahoot! school plans](https://kahoot.com/schools/plans/). The price is a planning input, not a purchase commitment.
- **Hybrid:** buy the same Kahoot! live-session service for $36 over four months and build only quiz authoring, analytics and export. The listed feature estimates for those modules are 44 + 30 + 24 = 98 h; integration effort and compatibility are not separately estimated, so this score is provisional.

## Weights, fixed before scoring

Weights were set on 2026-10-27 before assigning option scores; the learning objective receives the largest weight, followed by cash, then the fixed pilot date and requirement fit. Learning value (40): this is a Software Engineering capstone, so retain the most weight for what the team learns. Cost (25): the cash cap is fixed at 200 USD. Time (20): the week-14 pilot date is fixed, but time can be compared after cash and learning. Fit (15): all 47 functional requirements matter, but the pilot can flex lower-priority scope. Total = 40 + 25 + 20 + 15 = 100.

## Scores and evidence

Score scale: 1 = least favorable and 5 = most favorable. For cost, 5 means no more than 25 % of the 200 USD cap, 4 means 26–75 %, 3 means 76–100 %, 2 means 101–150 %, and 1 means more than 150 %.

| Criterion | Weight | Build | Buy | Hybrid |
| --------- | ------ | ----- | --- | ------- |
| Learning value for the capstone | 40 | 5 | 1 | 3 |
| Cost within the 200 USD cash budget | 25 | 3 | 5 | 5 |
| Time to the week-14 pilot | 20 | 3 | 5 | 4 |
| Fit to the 47 functional requirements | 15 | 5 | 2 | 4 |
| **Weighted score** | | **410** | **295** | **385** |
| **Percent of 500** | | **82 %** | **59 %** | **77 %** |

- **Learning:** Build scores 5 because it performs the capstone as planned; Buy scores 1 because the live quiz product is purchased rather than engineered; Hybrid scores 3 because authoring, analytics and export remain team-built.
- **Cost:** Build scores 3 because the 200 USD plan uses 100 % of the cap; Buy scores 5 because $9 × 4 months = $36, or 18 %; Hybrid scores 5 because its quoted live-service cash is also $36, or 18 %, while its build labor stays within the planned team effort.
- **Time:** Build scores 3 because it uses the full planned 504 h before the 56 h contingency; Buy scores 5 because an existing hosted service avoids building the live-session engine; Hybrid scores 4 because it avoids building that engine but still needs 98 h of listed authoring, analytics and export work plus unestimated integration.
- **Fit:** Build scores 5 because it is planned against the 47 functional requirements; Buy scores 2 because the cited school plan verifies live quizzes and 50 participants but does not demonstrate coverage of the 47 project requirements; Hybrid scores 4 because the named custom modules remain built to those requirements, while the bought-engine integration is unverified.

Build calculation = 40×5 + 25×3 + 20×3 + 15×5 = 200 + 75 + 60 + 75 = 410. Buy = 40×1 + 25×5 + 20×5 + 15×2 = 295. Hybrid = 40×3 + 25×5 + 20×4 + 15×4 = 385.

## Sensitivity check

Move 10 points from the heaviest criterion (learning) to the lightest (fit): learning 30, cost 25, time 20, fit 25; sum = 100.

- Build = 30×5 + 25×3 + 20×3 + 25×5 = 410.
- Buy = 30×1 + 25×5 + 20×5 + 25×2 = 305.
- Hybrid = 30×3 + 25×5 + 20×4 + 25×4 = 395.

Winner unchanged: Build. These scores are a decision aid; confirm the SaaS terms and hybrid integration before authorizing a purchase.
