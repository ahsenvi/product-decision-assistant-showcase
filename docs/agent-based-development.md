# Agent-based development

How AI Product Decision Intelligence is planned, built and verified. The owner sets goals, scope and business decisions. Claude Code agents carry out planning, development, testing and tracking inside that approved scope. Prompts, repository settings and infrastructure details aren't published.

## Implemented

- **Roles.** Each role has its own instruction file: coordinator, sprint planner, developer, QA reviewer, market researcher, legal-preparation researcher and product marketer. At most one sub-agent works at a time.
- **Issue-driven backlog.** GitHub Issues and Projects are the only backlog. A task is worked on only after the owner approves it through a status label.
- **Branch discipline.** One task per branch, draft pull requests only and no direct pushes to `main`.
- **Verification before a pull request.** Tests, type check, lint and build run locally and in CI. A separate QA role reviews against the issue's acceptance criteria and reports passed, failed and could-not-run checks separately. A test is never deleted, skipped or weakened, and at most two fix attempts are made for the same failure.
- **Merge policy.** The owner merges anything touching prompts, schemas, UI, message text, dependencies, CI, agent instructions, workflow, legal or marketing files. Other changes, such as research reports, may be merged by the coordinator only after QA approval and passing CI.
- **Project-board sync.** A GitHub Actions workflow mirrors status labels onto a Projects board, because cloud sessions can change labels but not board fields.
- **Spend and decision limits.** Paid model use only for approved tasks, with a monthly budget and a per-run cap. Product, UX, architecture, paid-spend, data, legal and release decisions go to the owner as decision issues.
- **Research discipline.** Findings, inferences and assumptions to verify are kept apart. Each source has an access date, and reports state numbers only when measured.

## Not implemented or limited

- Cloud sessions can't read the project board and have no model API key, so paid evaluations run locally.
- There is no autonomous merge of product-affecting changes and no automated deployment.
- This process was run mostly on one product. I haven't measured delivery speed or defect rates against a human-only baseline.
