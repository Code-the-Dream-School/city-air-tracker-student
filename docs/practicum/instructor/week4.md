# Week 4: Transform Layer and Gold Data Contract

Week 4 is where raw extract data becomes useful analytical data.
Students should take the raw response shape and storage decisions from Weeks 2 and 3, then build the transform layer that produces clean, predictable gold records.
The goal is to create a trusted data contract that the load layer, tests, and later dashboard work can depend on.

The AIR and PR references below point back to this instructor reference repo.
Use them as planning breadcrumbs and examples of the kind of work that will eventually exist in the student project.
Primary guideposts for Week 4 are AIR-012 for the gold data contract and AIR-007 for the dashboard-ready data shape.
Some references touch dashboard behavior, but Week 4 should focus on the data shape and verification.
Frontend implementation can remain a later responsibility.

| Week 4 item | Related repo references | Practicum support or student deliverable? | What students should do | Story points |
|---|---|---|---|---|
| Week 3 handoff review | AIR-012.5, AIR-012.9, AIR-012.10; PRs #74, #81, #83 | Student deliverable from Week 3, used in Week 4 | Review the raw response metadata, gold table keys, and upsert rules before writing transform code. If the expected input/output shape is unclear, resolve that first. | N/A |
| Transform acceptance criteria | AIR-012.8, AIR-012.10, AIR-012.11, AIR-007.3; PRs #78, #83, #85, #92 | Practicum support material | Instructors should clarify the minimum transform goals: required output columns, derived fields, expected row grain, null handling, tests, and dashboard-facing fields. | N/A |
| Raw response reader or adapter | AIR-012.8; PR #78 | Student deliverable | Create the transform-side input boundary. Students should be able to read raw records from the storage layer or from fixtures that match the Week 3 raw response contract. | 3 |
| Raw-to-gold transformation | AIR-012.8; PR #78 | Student deliverable | Convert raw OpenWeather response data into gold rows. Each row should represent the chosen observation grain, include city/location context, and keep pollutant/AQI values in predictable columns. | 8 |
| Derived AQI and risk fields | AIR-012.8; PR #78 | Student deliverable | Add derived fields that help later users interpret the data, such as AQI category labels, risk scoring, or other agreed-on summary values. Students should document any formula or rule they use. | 3 |
| Gold data contract | AIR-012.9, AIR-012.10; PRs #81, #83 | Student deliverable | Finalize the gold output schema. Students should define required columns, data types, unique keys, upsert behavior, and the row shape expected by the load layer. | 5 |
| Load-layer integration check | AIR-012.10; PR #83 | Student deliverable | Connect the transform output to the Week 3 load/upsert path using sample or real raw records. Students should verify that transformed rows can be written without breaking the storage contract. | 5 |
| Regression and integration tests | AIR-012.11; PR #85 | Student deliverable | Add tests for representative raw payloads, empty payloads, missing optional fields, repeated records, and load integration. Tests should protect the data contract from accidental drift. | 5 |
| Dashboard-ready data shape | AIR-007.3; PR #92 | Student deliverable with later handoff | Identify the fields the dashboard/API will need, such as latest observation by city, trend data, city comparison fields, and summary counts. This is a data contract, not the React implementation. | 3 |
| Data dictionary update | AIR-012.8, AIR-007.3; PRs #78, #92 | Student deliverable | Document the final gold fields in plain language so future teammates know what each column means and where it comes from. | 2 |
| Week 4 implementation PR | AIR-012.8, AIR-012.10, AIR-012.11, AIR-007.3; PRs #78, #83, #85, #92 | Student deliverable | Submit one or more PRs that show the transform layer and gold contract taking shape. The PR should include tests, a data dictionary update, and a handoff note for scheduler and dashboard work. | 2 |

**Total student story points:** 36

**Effort note:** Week 4 is another strong week because the transform, load integration, and test safety net all depend on each other. If the team needs relief, keep the core AIR-012 transform/load contract first and move the AIR-007 dashboard-ready data-shape note or final data dictionary polish into Week 6 documentation work.
