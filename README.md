# adf-factory

Git repo for the single shared Azure Data Factory (dev). Git root folder in ADF: `/adf`.

## Layout

- `adf/shared/` - platform-owned linked services, integration runtimes, reusable pipelines
- `adf/teams/teamA/`, `teamB/`, `teamC/` - each team's pipelines, datasets, data flows, triggers, linked services

## Workflow

1. Create a branch `feature/<team>/<name>` (for example `feature/teamA/load-sales`). Use `feature/platform/<name>` for shared changes.
2. Change only files in your own folder. The `path-check` workflow fails any PR that touches another team's folder.
3. Open a PR into `main`. CODEOWNERS reviewers must approve.
4. Only CI/CD publishes to the factory from `main`.
