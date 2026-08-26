## Code Quality & CI/CD Setup

### Code Quality & Linting

This project uses **ESLint** (configured in `eslint.config.ts`) and **Prettier** (`.prettierrc`) for static code analysis and formatting across TypeScript files.

### CI/CD Pipeline

GitHub Actions manages the automated workflow (`.github/workflows/ci.yml`). The workflow executes sequentially:

1. **`lint`**: Executes `npm run check` (ESLint & Prettier) prior to running tests.
2. **`api-tests` & `ui-tests`**: Runs API and UI test suites concurrently after the `lint` job successfully completes (`needs: lint`).

> **Note:** The API (`test/api/placeholder.api.ts`) and UI (`test/ui/placeholder.ui.ts`) test suites currently use stubbed placeholder functions to demonstrate pipeline execution rather than connecting to live environments.
