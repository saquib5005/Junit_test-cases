# AI Project Instructions

These instructions apply to all Jira, OpenSpec, coding, refactoring, debugging, and maintenance tasks in this project.

---

## 1. Before Making Changes

Before modifying any code:

1. Understand the Jira requirement or user request.
2. Inspect the existing code and relevant tests.
3. Read the relevant project knowledge from:
   - `brain/`
   - `docs/`
   - `requirements/`
   - `openspec/`
   - `test-audit/`
4. Do not read every file unnecessarily. Identify and read only the files relevant to the current task.
5. Identify the affected:
   - Modules
   - APIs
   - Database
   - Business rules
   - Dependencies
   - Tests
   - Documentation
   - OpenSpec specifications
6. Treat existing code and tests as evidence of the current system behavior.
7. Treat requirements as the desired behavior.
8. Never assume documentation is correct when it contradicts the actual code or tests.
9. If code, tests, documentation, requirements, or OpenSpec contradict each other, clearly report the conflict instead of guessing.

---

## 2. OpenSpec Workflow

For requirement-driven changes:

1. Understand the Jira requirement.
2. Inspect the existing implementation and relevant project knowledge.
3. Identify the impact of the requested change.
4. Create or update the appropriate OpenSpec change.
5. Ensure the OpenSpec accurately describes the desired behavior.
6. Review the OpenSpec before implementing the change.
7. Implement the code according to the approved OpenSpec.
8. Run the relevant tests.
9. Validate the implementation against the OpenSpec and requirements.

Do not make code changes based only on the Jira description when additional project context, existing behavior, or OpenSpec information is available.

---

## 3. Existing Code and Refactoring

When modifying or rewriting existing code:

1. Understand the current implementation before deleting or replacing it.
2. Read `brain/current-behavior.md` when relevant.
3. Inspect existing tests to understand currently expected behavior.
4. Identify important behavior that must be preserved.
5. If the desired behavior differs from the current behavior, make the difference explicit in the OpenSpec.
6. Do not assume that removing existing code means its behavior is no longer required.
7. After rewriting, verify the new implementation against the OpenSpec and relevant tests.

---

## 4. Documentation and Knowledge Sync

After implementing a change, determine whether the change affects project knowledge.

Update ONLY the relevant Markdown files inside:

- `brain/`
- `docs/`
- `test-audit/`

Do not update every Markdown file after every change.

### `brain/`

- `memory.md`
  - Update important long-term project context.

- `decisions.md`
  - Update when an architectural, technical, or design decision is introduced or changed.
  - Include the decision and its reason when known.

- `domain.md`
  - Update when domain concepts, entities, relationships, or terminology change.

- `business-rules.md`
  - Update when business rules or business logic change.

- `current-behavior.md`
  - Update when the actual behavior of the existing system changes.

- `dependencies.md`
  - Update when libraries, services, APIs, integrations, or external dependencies change.

### `docs/`

Update the relevant documentation when applicable:

- `overview.md`
  - Overall system purpose or major functionality changes.

- `architecture.md`
  - Components, services, architecture, or data flow changes.

- `api.md`
  - API endpoints, request/response formats, authentication, or API behavior changes.

- `database.md`
  - Database schema, relationships, queries, migrations, or data models change.

- `infrastructure.md`
  - Infrastructure, environments, cloud resources, networking, or configuration changes.

- `security.md`
  - Authentication, authorization, permissions, security controls, or sensitive-data handling changes.

- `deployment.md`
  - Build, deployment, release, or environment procedures change.

### `test-audit/`

- `validation.md`
  - Update when acceptance criteria or validation rules change.

- `test-strategy.md`
  - Update when the testing approach or required test types change.

- `audit-checklist.md`
  - Update when new verification or review requirements are introduced.

- `known-issues.md`
  - Update when a known bug, limitation, or technical debt item is introduced, resolved, or changed.

---

## 5. Documentation Rules

When updating Markdown files:

1. Update only files affected by the change.
2. Do not modify unrelated documentation.
3. Do not invent information.
4. Do not silently resolve conflicts.
5. Do not duplicate the same information across multiple files.
6. Preserve useful existing information.
7. Keep documentation concise and accurate.
8. Documentation must reflect the final implemented behavior.
9. If something cannot be determined from the code, tests, requirements, or project history, explicitly mark it as unknown rather than guessing.
10. Do not change documentation merely to make it agree with an incorrect implementation. Identify the problem first.

---

## 6. Final Validation

Before considering a Jira/OpenSpec task complete:

1. Verify the implementation against the approved OpenSpec.
2. Verify the implementation against the Jira requirement.
3. Run relevant tests.
4. Check for regressions in affected functionality.
5. Check whether `brain/`, `docs/`, or `test-audit/` contain outdated information.
6. Update only the affected Markdown files.
7. Confirm that the final code, tests, OpenSpec, and relevant documentation are consistent.
8. Report any unresolved conflicts, assumptions, or known limitations.

---

## 7. General Rules

- Do not invent requirements, behavior, architecture, or technical decisions.
- Do not make unnecessary changes outside the scope of the task.
- Prefer existing project patterns over introducing new patterns.
- Reuse existing utilities, services, and conventions when appropriate.
- Keep changes focused and minimal.
- Do not modify tests simply to make failing tests pass unless the expected behavior has intentionally changed.
- When behavior changes intentionally, update the relevant tests and documentation.
- When uncertain, inspect the code, tests, OpenSpec, and project knowledge before making a decision.
