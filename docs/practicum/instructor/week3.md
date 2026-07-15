# Week 3: Storage, PostgreSQL, and Load Contracts

Week 3 is where the project gets a real persistence layer.
Students should take the extract contracts from Week 2 and decide how city data, geocoding results, raw API responses, pipeline run status, and eventual gold records will be stored.
The goal is to make later pipeline stages easier to build, not to finish every downstream feature at once.

The AIR and PR references below point back to this instructor reference repo.
Use them as planning breadcrumbs and examples of the kind of work that will eventually exist in the student project.
Primary guideposts for Week 3 are AIR-012 for PostgreSQL-first persistence and AIR-009 for Parquet/archive storage.
Some of these references touch transform output and optional archive output, but Week 3 should focus on database design, migrations, persistence functions, and verification.
The real transform logic can remain a Week 4 responsibility.

| Week 3 item | Related repo references | Practicum support or student deliverable? | What students should do | Story points |
|---|---|---|---|---|
| Week 2 handoff review | AIR-012.4, AIR-012.5, AIR-012.6; PRs #72-74 | Student deliverable from Week 2, used in Week 3 | Review the city loader interface, geocoding cache contract, raw response metadata contract, and fresh-start notes before designing persistence. | N/A |
| Persistence acceptance criteria | AIR-009.x, AIR-012.x; PRs #65, #66, #69-74, #76, #81, #83, #87, #89, #95 | Practicum support material | Instructors should clarify the minimum storage goals: what must be stored in PostgreSQL, what can be exported as Parquet or archive output, and what verification is expected by the end of the week. | N/A |
| PostgreSQL schema design | AIR-012.1; PRs #66, #69 | Student deliverable | Design the core tables needed for cities, geocoding cache, raw air-pollution responses, pipeline runs, and gold records. Students should explain primary keys, foreign keys, uniqueness rules, and required fields. | 5 |
| Migration/bootstrap workflow | AIR-012.2; PR #70 | Student deliverable | Add a repeatable way to create or update the database schema. Students should be able to start from an empty database and apply the schema without manual table creation. | 5 |
| City persistence and seed/import path | AIR-012.4; PR #72 | Student deliverable | Store city input records in PostgreSQL and provide a seed/import path from the configured city file. This is the database-backed version of the Week 2 city loader work. | 5 |
| Geocoding cache persistence | AIR-012.6; PR #73 | Student deliverable | Persist geocoding results so repeated pipeline runs can reuse coordinates. Students should handle cache lookup, cache write, and the shape of a cached result. | 5 |
| Raw response persistence | AIR-012.5; PR #74 | Student deliverable | Store raw OpenWeather responses and the metadata defined in Week 2. Students should preserve enough raw data for the transform layer to rebuild gold records later. | 5 |
| Pipeline run tracking | AIR-012.7; PR #76 | Student deliverable | Track pipeline run status and useful counts, such as city count, raw response count, gold row count, start/end time, and failure message. | 3 |
| Gold table keys and upsert rules | AIR-012.9, AIR-012.10; PRs #81, #83 | Student deliverable with Week 4 handoff | Define how gold records will be identified and updated. Students can test the load function with sample records while the real transform logic is still being built. | 5 |
| Optional Parquet/archive output | AIR-009.x; PRs #65, #95 | Stretch or instructor-guided deliverable | Decide whether the cohort needs optional Parquet export or archive-storage output in this practicum. If included, keep it secondary to the PostgreSQL path and document when it should run. | 5 |
| Local storage workflow documentation | AIR-012.12, AIR-012.13; PRs #87, #89 | Student deliverable | Document how to initialize storage, seed cities, run the persistence checks, and verify rows in the database. This should be practical enough for another team to follow. | 3 |
| Week 3 implementation PR | AIR-009.x, AIR-012.1, AIR-012.2, AIR-012.3, AIR-012.4, AIR-012.5, AIR-012.6, AIR-012.7, AIR-012.9, AIR-012.10, AIR-012.12, AIR-012.13; PRs #65, #66, #69-74, #76, #81, #83, #87, #89, #95 | Student deliverable | Submit one or more PRs that show the storage layer taking shape. The PR should include migrations, persistence functions, tests or verification notes, optional archive output if included, and a Week 4 handoff for transform expectations. | 2 |

**Total student story points:** 38 core, 43 with optional Parquet/archive output

**Effort note:** Week 3 is one of the heaviest weeks because schema design, migrations, and persistence all land together. If the team is overloaded, keep AIR-009 as instructor-guided or move the optional Parquet/archive output out of the core plan; if needed, pipeline run tracking can also be simplified and revisited during Week 5 runtime work.
