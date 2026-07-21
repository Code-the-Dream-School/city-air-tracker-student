# City Air Tracker

This repo contains a Code the Dream-friendly batch ETL project that:

1. Geocodes global cities to lat/lon
2. Pulls OpenWeather Air Pollution historical data
3. Transforms PostgreSQL-backed raw response records into a gold dataset
4. Writes the gold dataset to PostgreSQL
5. Serves a React dashboard backed by a Python API over PostgreSQL data

The pipeline uses DB-first gold persistence by default, with PostgreSQL as the primary gold-data target
City configuration, geocoding cache, and raw extract persistence are in PostgreSQL as runtime state.
The same PostgreSQL runtime path can target either local Docker/Postgres or managed Azure Database for PostgreSQL through environment configuration.

## Additional docs

Browse `docs/README.md` for the full categorized index.

- `docs/setup/local_postgresql_first_workflow.md`
- `docs/setup/run_and_debug_guide.md`
- `docs/setup/github_quality_gates_setup.md`
- `docs/collaboration/github_feature_branch_pr_guide.md`
- `docs/collaboration/pr_review_best_practices.md`
- `docs/collaboration/what_is_a_data_pipeline.md`
- `docs/architecture/architecture.md`
- `docs/architecture/data_flow_diagram.md`
- `docs/architecture/postgresql_schema_design.md`
- `docs/reference/data_dictionary.md`
- `docs/reference/openweather_environmental_api_fields_reference.md`
