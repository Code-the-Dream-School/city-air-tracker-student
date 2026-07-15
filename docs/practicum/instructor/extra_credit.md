# Week 7: Optional Extensions

Week 7 is an optional extension menu.
Teams should not try to complete everything here.
Instructors can use this list to help teams pick one focused stretch task based on interest, remaining time, and project stability.

The AIR and PR references below point back to this instructor reference repo.
Use them as planning breadcrumbs and examples of the kind of work that could extend the core project.
Primary guideposts for Week 7 are AIR-013 for hosted Azure services and deployment, AIR-014 for local ML enrichment, AIR-015 for synthetic demo data, and AIR-006/AIR-008 for forecasting.

Use the shared story point scale in [project_rubric.md](./project_rubric.md).

| Title | Description | Related repo reference | Story points |
|---|---|---|---|
| API health check status | Add a visible health/status indicator that tells users whether the dashboard API is reachable and returning valid data. This could include a small status badge, `/health` endpoint, and fallback messaging when the API is unavailable. | AIR-007; PRs #90, #92, #93 | 2 |
| City picker in the React app | Let users choose the city shown in the dashboard. The city picker should load available cities from the API, update dashboard views, and handle missing or empty city lists gracefully. | AIR-007; PRs #90, #92, #93 | 3 |
| Run ETL from the React app | Add a controlled UI path for triggering a new ETL run from the dashboard. This should include a button, disabled/loading states, success/failure feedback, and guardrails so users cannot accidentally spam pipeline runs. | AIR-007, AIR-011; PRs #67, #68, #94, #137, #146, #147 | 13 |
| Dashboard display settings | Add simple UI controls that let users configure how the app looks or behaves, such as default city, preferred chart view, visible metrics, or light/dark mode. Persist settings locally if practical. | AIR-007; PRs #90, #93 | 5 |
| User/admin login and permissions | Add authentication and role-based permissions so only admins can trigger ETL runs or change app settings, while regular users can view dashboard data. | New extension proposal | 13 |
| Hosted Azure service and deployment | Prepare the app for hosted deployment, including service configuration, deployment workflow, secrets, and repeatable setup documentation. This is where Azure service work belongs if the cohort is ready for it. | AIR-013; PRs #138, #139, #148, #149, #155; issues #140, #142 | 13 |
| Managed PostgreSQL environment | Configure the project to use a managed PostgreSQL service instead of only local database runtime. Include connection settings, secret handling, migration guidance, and verification steps. | AIR-013; PR #139; issues #98, #140 | 8 |
| 7-day air-quality forecast | Generate forecasted air-quality values and risk scores for upcoming days. Keep the first version explainable, testable, and clear about its assumptions. | AIR-006, AIR-008; no direct PR reference yet | 13 |
| Forecast dashboard view | Add a dashboard view for forecast results, including selected city, forecast horizon, risk category, model run timestamp, and empty/error states. | AIR-008, AIR-007; PRs #90, #92, #93 | 8 |
| Local ML risk enrichment | Add a local ML enrichment path that predicts a risk bucket or similar output from historical data. Include feature engineering, offline training, optional inference, and documentation. | AIR-014; open PR #150; issues #104-#107, #124-#126 | 13 |
| ML prediction dashboard panel | Display stored ML predictions in the React dashboard with a clear timestamp, explanation label, and fallback state when predictions have not been generated yet. | AIR-014, AIR-007; open PR #150; PRs #90, #92, #93 | 8 |
| Synthetic data mode | Add or improve synthetic air-pollution data support so the app can be tested and demoed without depending on a live OpenWeather API key. | AIR-015; open PRs #151-#153; issues #113-#117 | 8 |
| Recurring schedule polish | Improve the recurring scheduler path with configurable cadence, validation, tests, and documentation. This is a good fit for teams that enjoyed the runtime/orchestration layer. | AIR-011; PRs #137, #146, #147; open PR #154; issues #120-#123 | 8 |
| Synthetic-data dashboard validation | Verify that the dashboard works against synthetic pipeline output and fix any assumptions that only work with live API data. | AIR-015, AIR-007; open PRs #151-#153; PRs #90, #92, #93; issue #118 | 5 |
| Final demo hardening | Add polish that improves the final presentation: seeded demo data, a one-command demo script, screenshots, troubleshooting notes, or a short instructor-facing demo checklist. | AIR-002, AIR-007, AIR-015; PRs #50, #90, #92, #93; open PRs #151-#153 | 3 |

**Total available optional story points:** 123

**Effort note:** Week 7 is a menu, not a backlog to finish. A healthy team target is usually one 8-13 point extension, or a pair of smaller 2-5 point polish tasks if the team is recovering from the core build; anything larger than that should be split across students carefully or held for a future cohort.
