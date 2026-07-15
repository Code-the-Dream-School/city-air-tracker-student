# Week 2: Extract Layer and Raw Data Contracts

Week 2 is where students start turning the Week 1 plan into working project pieces.
The focus is the extract layer: city inputs, validation, API-facing code, mockable boundaries, and the raw data shape that later stages will depend on.
They should be building the first useful slice of the pipeline.

The AIR and PR references below point back to this instructor reference repo.
Use them as planning breadcrumbs and examples of the kind of work that will eventually exist in the student project.
Primary guideposts for Week 2 are AIR-003 and AIR-004 for city input handling and extract setup.
Some PostgreSQL-backed behavior appears in these references, but Week 2 should focus on extract contracts and testable boundaries.
The database-specific implementation can be handed off into Week 3.

| Week 2 item | Related repo references | Practicum support or student deliverable? | What students should do | Story points |
|---|---|---|---|---|
| Week 1 handoff review | AIR-005, AIR-134; PRs #14, #135 | Student deliverable from Week 1, used in Week 2 | Use the Week 1 city input contract, target architecture diagram, and runtime flow as the starting point for implementation. If those artifacts are unclear, tighten them before coding. | N/A |
| Extract acceptance criteria | AIR-003, AIR-004, AIR-012.4, AIR-012.5, AIR-012.6, AIR-109; PRs #11, #12, #72-74, #112 | Practicum support material | Instructors should clarify what the extract layer must handle: valid/invalid city rows, configurable city input, geocoding, OpenWeather requests, raw response shape, and clean-start behavior. | N/A |
| City file configuration | AIR-004, AIR-005; PRs #12, #14 | Student deliverable | Implement the configuration path for city input. Students should be able to explain where the city file path comes from and how the extract layer finds it. | 3 |
| City row validation | AIR-003; PR #11 | Student deliverable | Implement city row parsing and validation. Blank, missing, or invalid `city` and `country_code` values should be skipped or reported clearly, with tests for expected behavior. | 3 |
| City loader interface | AIR-012.4; PR #72 | Student deliverable | Create the extract-side city loader that returns the city records the rest of the extract layer needs. If PostgreSQL is not ready yet, define the interface now and use a file-backed or test-backed implementation. | 3 |
| Geocoding client and cache contract | AIR-012.6; PR #73 | Student deliverable | Create a geocoding boundary that can be tested without calling the real API every time. Students should define what cache data is needed, even if the PostgreSQL cache is implemented in Week 3. | 5 |
| OpenWeather raw extract client | AIR-012.5; PR #74 | Student deliverable | Build the API-facing code that fetches or simulates raw OpenWeather air-pollution responses. The code should keep the raw payload shape available for later transform work. | 5 |
| Raw response metadata contract | AIR-012.5; PR #74 | Student deliverable with Week 3 handoff | Define the metadata that should travel with each raw response, such as city identity, coordinates, request window, response timestamp, and record count. Hand off any database storage needs to Week 3. | 3 |
| Fresh-start extract checks | AIR-109; PR #112 | Student deliverable | Add tests or manual verification notes for first-run conditions: missing city file, empty city file, invalid city rows, no cached geocoding data, and predictable error messages. | 3 |
| Week 2 implementation PR | AIR-003, AIR-004, AIR-012.4, AIR-012.5, AIR-012.6, AIR-109; PRs #11, #12, #72-74, #112 | Student deliverable | Submit one or more PRs that show the extract layer taking shape. The PR should include focused tests and a short handoff note for any persistence work that belongs in Week 3. | 2 |

**Total student story points:** 27

**Effort note:** Week 2 is a medium build week and should feel like the first real implementation push. If teams are moving quickly, they can start outlining the Week 3 AIR-012 persistence contract; if they are struggling, keep the OpenWeather client mocked and move deeper API polish into a later week.
