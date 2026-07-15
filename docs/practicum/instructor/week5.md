# Week 5: Pipeline Runtime, Scheduling, and Observability

Week 5 is where the separate pipeline pieces become one coordinated runtime.
Students should connect extract, transform, and load through a shared runner, keep manual execution working, and add enough configuration and logging for the team to understand what happened during a run.
The goal is not just to run code once.
The goal is to make the pipeline repeatable, observable, and ready for scheduling.

The AIR and PR references below point back to this instructor reference repo.
Use them as planning breadcrumbs and examples of the kind of work that will eventually exist in the student project.
Primary guideposts for Week 5 are AIR-011 for runtime/orchestration and AIR-010 for scheduling and validation.
Week 5 should focus on pipeline runtime behavior, local configuration, and environment readiness.
Service hosting can remain an optional Week 7 responsibility.

| Week 5 item | Related repo references | Practicum support or student deliverable? | What students should do | Story points |
|---|---|---|---|---|
| Week 4 handoff review | AIR-012.8, AIR-012.10, AIR-012.11; PRs #78, #83, #85 | Student deliverable from Week 4, used in Week 5 | Review the transform/load contract and tests before wiring the full pipeline runner. If extract, transform, and load do not agree on data shape, resolve that before scheduling work. | N/A |
| Runtime acceptance criteria | AIR-010.x, AIR-011.x; PRs #67, #68, #94, #137, #146, #147 | Practicum support material | Instructors should clarify the minimum runtime goals: manual run behavior, shared runner boundaries, schedule expectations, logging, validation, and local environment requirements. | N/A |
| Shared pipeline runner | AIR-011.1a, AIR-011.2, AIR-011.3; PRs #67, #68, #94 | Student deliverable | Create a reusable runner that calls extract, transform, and load in order. The runner should return useful run information and avoid hiding errors. | 8 |
| CLI entrypoint and manual run path | AIR-011.1b, AIR-011.1c, AIR-010.6; PRs #68, #94, #146 | Student deliverable | Provide a command-line path for running the pipeline manually. Students should preserve the manual workflow while routing it through the shared runner. | 5 |
| Runtime logging and observability | AIR-011.4, AIR-010.4; PR #147 | Student deliverable | Add clear log messages around pipeline start, extract, transform, load, success, and failure. Logs should help a teammate understand where a run failed. | 3 |
| Runner tests and regression checks | AIR-011.1c, AIR-011.5, AIR-010.8; PRs #94, #146 | Student deliverable | Add tests for the runner, manual CLI path, success cases, and failure cases. Students should prove that the runner calls stages in the right order and reports failures clearly. | 5 |
| Prefect or scheduler entrypoint | AIR-010.1, AIR-010.2, AIR-011.7; PRs #137, #146 | Student deliverable or instructor-guided deliverable | Add a scheduler-friendly entrypoint. If the cohort uses Prefect, this should wrap the shared runner without duplicating pipeline logic. | 5 |
| Schedule configuration plan | AIR-010.1, AIR-010.5; PRs #137, #146 | Student deliverable | Define how scheduled runs should be configured, including frequency, history window, environment variables, and where schedule settings should live. | 3 |
| Runtime configuration and secrets guidance | AIR-010.3, AIR-010.7 | Student deliverable with instructor support | Document the runtime settings needed for local runs. Students should explain what is safe to commit, what belongs in secrets, and how environment configuration should work. | 3 |
| Scheduled run validation | AIR-010.8; PRs #137, #146 | Student deliverable | Add a basic way to validate a scheduled or scheduler-style run: status, logs, expected database writes, and useful failure output. | 3 |
| Week 5 implementation PR | AIR-010.x, AIR-011.x; PRs #67, #68, #94, #137, #146, #147 | Student deliverable | Submit one or more PRs that show the runtime layer taking shape. The PR should include the runner, entrypoints, logging, tests, configuration notes, and a Week 6 handoff for dashboard/API integration. | 2 |

**Total student story points:** 37

**Effort note:** Week 5 is a strong week and should be protected from scope creep. If students are behind, keep the shared AIR-011 runner and manual CLI path as the core work, then move the AIR-010 scheduler entrypoint or scheduled-run validation into Week 7 optional extension work.
