# Project Milestones

## Suggested Week 1 Turn-In

By the end of Week 1, each team should submit:

1. A link to a practice PR that went through review.
2. A short product and pipeline summary written in their own words.
3. A target architecture diagram.
4. A planned runtime flow diagram or written runtime walkthrough.
5. A short city input contract.
6. A team working agreement.

## Suggested Week 2 Turn-In

By the end of Week 2, each team should submit:

1. A PR for city input configuration and validation.
2. A city loader interface or implementation.
3. A geocoding boundary with a clear cache contract.
4. A raw OpenWeather extract client or mocked extract client.
5. A short raw response metadata contract for the transform/load teams.
6. Tests or verification notes for fresh-start and invalid-input cases.
7. A Week 3 handoff note for PostgreSQL-backed city loading, geocoding cache, and raw response persistence.

## Suggested Week 3 Turn-In

By the end of Week 3, each team should submit:

1. A database schema design for cities, geocoding cache, raw responses, pipeline runs, and gold records.
2. A migration or bootstrap workflow that creates the schema from scratch.
3. A city seed/import path backed by PostgreSQL.
4. Persistence for geocoding cache records and raw OpenWeather responses.
5. Pipeline run tracking with status and useful row/count metadata.
6. Gold table key and upsert rules, tested with sample records.
7. Storage verification notes or tests.
8. Optional Parquet/archive-storage output and verification notes, if included.
9. A Week 4 handoff note explaining what raw data shape the transform layer should consume and what gold data shape the load layer expects.

## Suggested Week 4 Turn-In

By the end of Week 4, each team should submit:

1. A transform module or function that converts raw records into gold records.
2. A documented gold data contract with required columns, types, keys, and upsert assumptions.
3. Derived AQI/risk fields with the rule or formula explained.
4. Integration with the Week 3 load/upsert path.
5. Regression tests for normal, empty, incomplete, and repeated raw payloads.
6. A dashboard-ready data shape note for later API/frontend work.
7. A data dictionary update.
8. A Week 5 handoff note explaining how the transform/load path should be called by the pipeline runner.

## Suggested Week 5 Turn-In

By the end of Week 5, each team should submit:

1. A shared pipeline runner that coordinates extract, transform, and load.
2. A manual CLI run path that uses the shared runner.
3. Runtime logs for stage start, stage completion, success, and failure.
4. Runner and CLI tests for success and failure cases.
5. A scheduler-friendly entrypoint or schedule configuration plan.
6. Runtime configuration and secrets guidance.
7. A validation note showing how the team knows a run completed successfully.
8. A Week 6 handoff note explaining what dashboard/API data is available and what runtime settings the frontend team will need.

## Suggested Week 6 Turn-In

By the end of Week 6, each team should submit:

1. A dashboard API or data-serving path connected to the gold data contract.
2. A React dashboard with useful summary and city-level views.
3. Loading, empty, and error states.
4. An end-to-end smoke test from pipeline output to dashboard display.
5. A documented local demo path.
6. Runtime configuration notes.
7. Final project documentation and known limitations.
8. A final demo that explains the product, architecture, data flow, team process, and tradeoffs.

## Suggested Week 7 Turn-In

By the end of Week 7, each team that chooses optional work should submit:

1. One selected optional task with a short scope statement.
2. A PR implementing the extension or a clearly documented partial implementation.
3. Tests, verification notes, or screenshots appropriate to the task.
4. Updated documentation explaining how to run, review, or maintain the extension.
5. A short reflection on what was completed, what remains, and whether the story-point estimate felt accurate.
