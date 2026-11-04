# Approach comparison · Realtime Quiz

Sources: [project profile](project-profile.md), [scoring sheet](approach-scoring.csv), [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow.md), [constraint analysis](../lab02/constraints.md)

| Approach   | How requirements are handled | How the sponsor controls the project (governance) | Week in which the sponsor first plays a working quiz | Two main risks | Fit with the Task 1 profile |
| ---------- | ---------------------------- | ------------------------------------------------- | ---------------------------------------------------: | -------------- | --------------------------- |
| Waterfall  | The eight Must features are frozen in a scope baseline at G1; every later change goes through a change request with written sponsor approval. | Plan approval at G1, then written status reports and change requests only; one stop/go decision at each of G2, G3 and G4, so the sponsor sees documents between the gates. | week 7 | 1. WebSocket proxy and Spring Boot 4 problems are discovered at integration in week 7, after the design is frozen, so rework lands on the fixed pilot date. 2. Nothing playable is shown before week 7, so feedback arrives after most of the effort (448 h) is already spent. | Poor: it answers the governance criterion well (20 x 4 = 80) but ignores technical uncertainty (25 x 2 = 50 of the 100 weighted points), which is a dominating criterion of the 3.05 hybrid profile. |
| Pure Scrum | The backlog is re-ordered every sprint; there is no baseline, so Must, Should and Could are re-negotiated at every review against the 504 h estimate. | The sponsor sees a working increment at a review every 2 weeks but has no gate to stop or re-plan; budget is tracked only by velocity, so there is no number to compare with the 560 h cap. | week 5 | 1. A first Scrum team without a plan drifts: sprint 1 committed 30 points and delivered 25, and the fixed week-14 pilot date is not protected by any baseline. 2. Scope creep from Could features (82 h) is only visible at the next review, because nothing is measured against a plan. | Medium: strong on the two adaptive criteria (25 x 5 = 125 and 15 x 5 = 75) but weak on governance (20 x 2 = 40) and on team inexperience (15 x 2 = 30). |
| Hybrid      | The scope baseline and the WBS are approved at G1; inside that frame the product backlog with FR ids is re-ordered every sprint, and changes above the stage tolerance go through a change request. | Four phase gates G1-G4 with five measurable criteria each, per-stage tolerances (hours, time, scope, quality, risk) and a weekly highlight report; the sponsor stops or re-plans at a gate instead of after the fact. | week 5 | 1. Two sources of truth (approved plan and product backlog) drift apart and create duplicate reporting. 2. Gate plus ceremony overhead on a 4-student team of 560 h can eat delivery capacity if the gates are run as document exercises. | Best: it matches the 3.05 hybrid band, keeps the governance points (20 x 5 = 100) and still earns the feedback points (15 x 4 = 60); it shows the sponsor a working quiz in week 5 exactly like Scrum. |

Columns: how requirements are handled · how the sponsor controls the project (governance) · week in which the sponsor first plays a working quiz · two main risks · fit with the Task 1 profile

## Weighted score (from approach-scoring.csv)

Weighted score = SUMPRODUCT(weight, fit) / 100 with the five weights of Task 1 (25, 25, 15, 20, 15). Waterfall 3.30 · Scrum 3.45 · Hybrid 4.05.

| Approach   | Weighted points (SUMPRODUCT) | Score |
| ---------- | ---------------------------: | ----: |
| Waterfall  |                          330 | 3.30  |
| Pure Scrum |                          345 | 3.45  |
| Hybrid     |                          405 | 4.05  |

The three scores are written into the last line of `approach-scoring.csv` as `weighted score,100,3.30,3.45,4.05`, so the numbers can be reproduced from the CSV with one SUMPRODUCT formula per column.

## Sensitivity

- Test 1: the hardest criterion to judge is *Team experience with agile* (a first Scrum team, so the score 2 is an assumption); moving its weight 15 -> 25 and taking 10 from *Requirements stability* (25 -> 15) gives waterfall 3.20, Scrum 3.35, hybrid 3.95, so the ranking stays hybrid, Scrum, waterfall.
- Test 2: moving 10 points from *Contract and governance constraints* (20 -> 10) to *Need for early delivery and feedback* (15 -> 25), which favours Scrum, gives waterfall 3.00, Scrum 3.75, hybrid 3.95, so the ranking is unchanged and Scrum only closes to 0.20 behind the hybrid.

Neither test changes the ranking: the hybrid stays first in both, and the gap to Scrum narrows from 0.60 to 0.20 at the widest.

## Recommendation

Choose the **hybrid** approach, scored **4.05** (405 of 500 weighted points), because it is the only candidate that is strong on both dominating criteria of the profile: it keeps two-week feedback loops for the uncertain technical core (technical uncertainty, weight 25) and keeps the plan baseline, gates and tolerances the sponsor demands (contract and governance constraints, weight 20). The runner-up is **pure Scrum at 3.45**; switch to it only if the sponsor drops the week-3 plan approval requirement and agrees to attend every sprint review as the single decision point, which removes the governance gap that costs Scrum 40 of its 100 governance points.
