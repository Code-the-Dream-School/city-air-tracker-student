# Week 1: Project Orientation and Team Workflow

Week 1 is about helping students understand the project they are about to build. The goal is to understand the product idea, agree on how the team will work, and create the first planning artifacts that will guide implementation.

The AIR and PR references below point back to this instructor reference repo. Primary guideposts for Week 1 are AIR-002 for workflow/onboarding and AIR-134 for architecture planning. Use them as planning breadcrumbs and examples of the kind of work that will eventually exist in the student project. The difference between the practicum and the courses taken in the past is the level of ambiguity. Most projects start with limited expectations and it is up to the team producing the work to decide on how to manage the work.

| Week 1 item | Related repo references | Practicum support or student deliverable? | What students should do | Story points |
|---|---|---|---|---|
| GitHub branch and PR workflow | AIR-002.1; PRs #10, #47 | Practicum support material | Read the workflow guide, then use it during the practice PR. Students should know how to create a branch, make a commit, push, create a PR, request review, and respond to feedback. | N/A |
| Pull request review expectations | AIR-002.2; PR #50 | Practicum support material | Use the review guide as a model for the team's working agreement. Students should understand what kind of feedback is helpful, how to ask questions, and how to revise without taking review personally. | N/A |
| Starter repo orientation | AIR-002.2, AIR-002.3; PRs #54, #56, #57 | Practicum support material | Review the repo structure and starter documentation. Students should identify what is already provided, what is intentionally missing, and where future work should live. | N/A |
| Local tooling expectations | AIR-002.1, AIR-002.2; PRs #47, #54 | Practicum support material | Confirm the development tools they will need for later weeks, such as Git, Python, Docker, and Node. | N/A |
| Quality gates and automated checks | AIR-001; PR #13 | Shared setup plus student responsibility | The practicum team should provide any starter checks. Students are responsible for understanding what the checks are for and getting their practice PR through the available review/check process. | N/A |
| Product and data pipeline summary | AIR-002.2; PR #50 | Student deliverable | Write a short explanation of the product in the team's own words: what problem it solves, what data it needs, and what the planned pipeline should do. | 2 |
| Target architecture diagram | AIR-134; PR #135 | Student deliverable | Draw the system the team plans to build. The diagram should include the planned extract, transform, load, storage, dashboard/API, frontend, and optional extension pieces. | 5 |
| Planned runtime flow | AIR-108; PR #109 | Student deliverable | Draw or describe what should happen when the future pipeline runs. Students should show the intended order of operations and where configuration, logs, database writes, and errors will fit. | 3 |
| City input contract | AIR-005; PR #14 | Student deliverable | Define the expected city input shape for the project. Students should explain the purpose of a city configuration file, what columns it needs, and how it will eventually feed the extract layer. | 2 |
| Practice PR | AIR-002.1, AIR-001; PRs #13, #47 | Student deliverable | Each team should submit one low-risk PR. Good options include the team working agreement, a planning artifact, or a small documentation clarification. | 2 |
| Team working agreement | No direct AIR reference | Student deliverable | Each team should decide how they will divide roles, communicate blockers, review code, rotate responsibilities, and keep work moving during the practicum. | 2 |

**Total student story points:** 16

**Effort note:** Week 1 is intentionally lighter than the build weeks so teams have room to form, ask messy questions, and understand the product. If a team finishes early, they can get a gentle head start on Week 2 by sketching the AIR-003 city validation rules or the AIR-004 city file configuration path.
