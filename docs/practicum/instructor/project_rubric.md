# Sample Practicum Rubric

Use this as a starting point for assigning work across the 6-week core practicum with an optional Week 7 extension menu.
Each team should adjust the scope based on group size, class pace, and instructor guidance.

## Instructor Note on AIR References

The AIR and PR references are not meant to be a strict one-to-one ticket assignment for each week.
Several AIR groups span multiple parts of the project, so the same family may appear in more than one week when it helps instructors connect student work back to the reference implementation.

Read each week as having a primary instructional thread plus supporting references.
For example, Week 5 is mainly an AIR-011 runtime/orchestration week, with AIR-010 schedule/validation work as a useful supporting reference.
Likewise, AIR-012 appears across Weeks 2-4 because extract contracts, persistence, and transform/load behavior all depend on each other.
AIR-009 is still a useful Week 3 reference for Parquet export and archive-storage thinking.
AIR-013 is held for optional Week 7 extension work so hosted-service work does not distract from the core six-week build.

## Story Point Scale

Story points are rough effort estimates for student-facing work.
They are meant to help instructors balance the weekly load, not to grade students by raw point totals.
They can also help instructors record each team's velocity: how many points the group tends to finish in a week while still producing understandable, reviewable work.
That pattern gives instructors a better sense of when to reduce scope, pair a team with extra support, or encourage a team to pull in stretch work.
Use `N/A` for practicum support materials, instructor-only setup, or handoff rows that were already counted in a previous week.

| Points | Effort meaning |
|---|---|
| 1 | Tiny polish or documentation cleanup |
| 2 | Small planning, documentation, or low-risk code task |
| 3 | Focused student deliverable with clear boundaries |
| 5 | Moderate feature, contract, or test set touching one or two parts of the project |
| 8 | Larger feature or integration path with meaningful cross-layer work |
| 13 | Large, risky, or multi-system feature that should usually be optional or split |

## Component Buckets

1. Foundation and collaboration
2. Extract layer and raw data contracts
3. Load layer, PostgreSQL storage, archive storage, and persistence implementation
4. Transform layer and gold data contract
5. Scheduler/data pipeline and observability
6. Frontend React, dashboard API, and demo
7. Optional extensions

## Week-by-Week Plan

| Week | Focus | Suggested scope | Student assignment | Estimated student points |
|---|---|---|---|---|
| 1 | Project orientation, Git workflow, architecture planning | AIR-001, AIR-002.x, AIR-005, AIR-108, AIR-134; PRs #10, #13, #14, #47, #50, #54, #56, #57, #109, #135. See [Week 1 project onboarding](./week1.md) for the support-material vs student-deliverable breakdown. | Understand the starter repo, practice the GitHub workflow, explain the planned product/data pipeline, create target architecture/runtime diagrams, define the city input contract, and agree on team working norms. | 16 |
| 2 | Extract layer and city/raw data contracts | AIR-003, AIR-004, AIR-012.4, AIR-012.5, AIR-012.6, AIR-109; PRs #11, #12, #72-74, #112. See [Week 2 extract layer](./week2.md) for the support-material vs student-deliverable breakdown. | Build city input configuration, invalid city handling, extract interfaces, geocoding/API boundaries, raw response metadata contracts, and the first fresh-start checks. | 27 |
| 3 | Load/storage and PostgreSQL-first backend | AIR-009.x, AIR-012.x; PRs #65, #66, #69-74, #76, #81, #83, #87, #89, #95. See [Week 3 storage layer](./week3.md) for the support-material vs student-deliverable breakdown. | Build schema and migrations, DB-first persistence for cities/geocoding/raw responses, pipeline run tracking, gold-table upsert rules, optional Parquet/archive output, and setup docs. | 38 core, 43 with optional archive output |
| 4 | Transform layer, data contract, and tests | AIR-012.8, AIR-012.10, AIR-012.11, AIR-007.3; PRs #78, #83, #85, #92. See [Week 4 transform layer](./week4.md) for the support-material vs student-deliverable breakdown. | Convert raw records into gold rows, validate output columns and keys, add integration/regression tests, document derived fields, and define the dashboard-ready data shape. | 36 |
| 5 | Scheduler/data pipeline runtime | AIR-010.x, AIR-011.x; PRs #67, #68, #94, #137, #146, #147. See [Week 5 pipeline runtime](./week5.md) for the support-material vs student-deliverable breakdown. | Create a reusable pipeline runner, wire the CLI/scheduler entrypoint, support manual runs, add logs and validation, and document runtime config and secrets. | 37 |
| 6 | Frontend React, API, and demo | AIR-007.x; PRs #45, #90, #92, #93. See [Week 6 dashboard and demo](./week6.md) for the support-material vs student-deliverable breakdown. | Finish the React dashboard, connect it to the PostgreSQL-backed API, complete final integration checks, and prepare the final demo and handoff docs. | 34 |
| 7 | Optional extensions | AIR-006, AIR-008, AIR-011, AIR-013, AIR-014, AIR-015, plus cohort-proposed enhancements. See [Week 7 optional extensions / extra credit](./extra_credit.md) for the extension menu and story-point estimates. | Pick extension work based on team interest, remaining time, and instructor guidance. | 123 available; recommend 8-13 selected |
