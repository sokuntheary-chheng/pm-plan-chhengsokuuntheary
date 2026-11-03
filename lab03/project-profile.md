# Project profile · Realtime Quiz

Sources: [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow.md), [constraint analysis](../lab02/constraints.md), [feature list](../lab02/features.csv), [stakeholder list](../lab01/stakeholders.md)

| #   | Criterion                            | Evidence (one fact) | Weight | Score 1-5 |    W x S |
| --- | ------------------------------------ | ------------------- | -----: | --------: | -------: |
| 1   | Requirements stability               | The charter fixes the eight Must features F01-F08 (300 h of the 504 h planned) as Must for the pilot, but no document specifies the screens or the exact real-time behaviour. |   25 |         3 |       75 |
| 2   | Technical uncertainty                | The charter lists the campus proxy blocking WebSocket and scarce Spring Boot 4 examples as high-level risks, so the transport may have to change to SockJS mid-project. |   25 |         4 |      100 |
| 3   | Team experience with agile           | This is the team's first Scrum project and Java and Spring are only being learned in the parallel Software Engineering course. |   15 |         2 |       30 |
| 4   | Contract and governance constraints  | Internal project with no contract, but the sponsor requires an approved plan by the end of week 3 and a fixed pilot in week 14 (charter sections 7 and 9). |   20 |         2 |       40 |
| 5   | Need for early delivery and feedback | The MVP demo is fixed in week 7 and the sponsor wants a working increment to play at every sprint review, while the pilot stays fixed in week 14. |   15 |         4 |       60 |
|     | **Profile** = SUM(W x S) / 100       |                     |    100 |           | **3.05** |
| 6   | (optional) Sponsor availability      | Charter section 9: the sponsor answers approvals within 5 working days, so an increment can be reviewed at each sprint review every 2 weeks. |      - |         4 |        - |

Score 1-5: 1 = the fact favours predictive, 5 = it favours adaptive.

Interpretation: < 2.5 predictive · 2.5-3.5 hybrid · > 3.5 agile

Weights sum: 25 + 25 + 15 + 20 + 15 = 100. Weighted points: 75 + 100 + 30 + 40 + 60 = 305, so the profile value is 305 / 100 = 3.05, which falls in the 2.5-3.5 hybrid band. Row 6 is excluded from the total, so the weights stay comparable with the class.

## Profile summary

The Realtime Quiz project is a fixed-date, fixed-budget project with a stable Must scope but an uncertain technical core, and its profile value of 3.05 lands in the hybrid band. The two dominating criteria are technical uncertainty (25 x 4 = 100 weighted points) and requirements stability (25 x 3 = 75 weighted points), which together carry half of the 305 weighted points. Task 2 must therefore compare a predictive candidate (waterfall), an adaptive candidate (pure Scrum) and a hybrid that wraps a predictive plan and phase gates around agile sprints.
