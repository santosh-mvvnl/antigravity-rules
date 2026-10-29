---
trigger: always_on
description: Universal Agent Rules & Global Development Standards for All Projects
---

# Universal Agent Rules & Global Development Standards

These rules are universally active and must be treated as mandatory development standards applied to all existing and future projects, modules, dashboards, reports, summaries, automation scrapers, and data-driven applications.

---

## Part 1: Universal Operational Rules

### 1. Mandatory Confirmation Before Codebase Changes
- Whenever the user sends a prompt, **always ask whether a codebase change is to be done or not** before creating, modifying, or deleting any files in the codebase.
- Do not modify project files until the user explicitly confirms that codebase changes are allowed for that request.

### 2. Automatic Git Add, Commit, and Push After Approved Changes
- Whenever a codebase change is approved by the user and applied, **immediately run the Git commands to stage, commit, and push the changes to GitHub** (when the project is a Git repository with a configured remote):
  1. `git add -A` (respecting `.gitignore` so secrets/local databases are never staged)
  2. `git commit -m "<concise descriptive commit message>"`
  3. `git push`

### 3. Mandatory Structured Response Sections
In every response addressing user prompts, issues, or implementation tasks, **always list out the following 6 sections**:
1. **Assumptions Made:** Always list out any assumptions you have made (or explicitly state `None` if no assumptions were made).
2. **Root Cause of Issue(s):** Always list out the root cause of any issue raised (or state `N/A — Feature / Configuration Request` when no defect is raised).
3. **Corrective Measures Taken:** Always list out the corrective measures taken (or proposed) to resolve the issues.
4. **Commands Executed:** Always list out the commands you have run.
5. **Important Functions, Packages, and Drivers Used:** Always list out the important functions, packages, drivers, and modules used in the codebase.
6. **Important Instructions for the User:** Always list out the important instructions for the user.

### 4. Strict Zero Synthetic Data Policy (Pure Authentic Portal Data)
- Complete prohibition of synthetic, mock, formula-derived, or placeholder data generation across all project layers, scrapers, automation drivers, controllers, APIs, and database storage.
- Never invent dummy names, artificial applicant identities, fake emails, synthetic phone numbers, mock receipts, fake meter serials, artificial objections, or arbitrary status defaults.
- All dashboard metrics, stage pendency breakdowns, administrative unit allocations, and application-wise dossiers must strictly reflect authentic source portal reports and authoritative datasets.
- When an individual data field, attribute, or subsection is genuinely absent or not published on the actual source portal, the system must strictly render `"-"`, empty lists, or clean informative notices ("Not Available on Portal") rather than fabricating placeholder records.
- 100% summary-to-list count parity must always be preserved through authentic source aggregation and verified upstream reconciliation.

### 5. Automatic Synchronization of Global Rules to `antigravity-rules` GitHub Repository
- Whenever any rule is created, updated, or removed in `global.md`:
  1. Immediately apply the modification to the local configuration (`~/.gemini/config/rules/global.md`) and the active project workspace (`.gemini/rules/global.md`).
  2. Synchronize the updated `global.md` to the central GitHub repository (`https://github.com/santosh-mvvnl/antigravity-rules.git`).
  3. Update the repository `README.md` to reflect the latest rule additions, descriptions, and summary checklists.
  4. Immediately execute the Git workflow (`git add -A`, `git commit -m "docs: Update global rules and README"`, `git push origin main`) to ensure all machines cloning or pulling from the repository stay synchronized.

---

## Part 2: Global Development & Data Standards

### 6. Summary Hyperlinks and Strict 1:1 Data Parity
Whenever a summary, dashboard, KPI card, aggregate table, or analytical report displays a numerical value representing a count of consumers, applications, accounts, records, or other entities:
- Make every displayed summary value clickable and link it to the corresponding detailed record list.
- Clicking a summary value must open or download the exact set of source records contributing to that value, with all applicable filters preserved.
- Enforce strict **1:1 count parity** between the displayed summary value and the number of corresponding detail rows in the linked or downloaded file.
- For example, if a summary cell displays `1,250`, the corresponding Excel or CSV file must contain exactly 1,250 qualifying data rows, excluding the header row.
- Ensure that summary aggregation and detail extraction use the same source data, filter conditions, business rules, status definitions, and date ranges.
- Prevent duplicate records, missing records, inconsistent joins, incorrect grouping, stale cached results, and mismatched filters from causing discrepancies.
- Where a summary represents distinct consumers or accounts, apply the same distinct-counting logic when generating the detailed file.
- For multi-dimensional summaries, preserve all applicable dimensions and filters when opening the corresponding detail list.
- Validate count parity programmatically before presenting or downloading the results. If validation fails, identify and log the discrepancy instead of silently presenting inconsistent data.
- **Mandatory acceptance criterion:** Every clickable summary count must reconcile exactly with the number of qualifying data rows in its corresponding downloaded file.

### 7. Contextual Dropdown Filters with Checkboxes Above Summaries (Excel AutoFilter Semantics)
Whenever a summary or dashboard is generated from source data, analyze the source schema and provide relevant multi-select dropdown filters with checkboxes above the summary.
- **Adjacent Checkboxes:** Display individual checkboxes positioned immediately adjacent to each option in the dropdown list, allowing users to explicitly select or unselect individual items.
- **Default State — All Checked:** Default to all options checked (`value=True`) so the complete dataset is presented initially upon loading, with instant capabilities to select all, clear all, or toggle individual items.
- **Top Search Box (Excel AutoFilter Style):** Position a dedicated search text input box permanently at the very top of each filter popover/dropdown, enabling instantaneous real-time filtering across long option lists.
- **`(Select All Search Results)` Checkbox:** When text is entered in the search box, dynamically present a `(Select All Search Results)` master checkbox displaying the count of matching items to select or deselect all search matches in a single click.
- **`Add current selection to filter` Checkbox:** When searching, provide an `Add current selection to filter` checkbox:
  - If unchecked (default — matching Microsoft Excel AutoFilter standard): Selecting search results isolates them, replacing previous selections with only the searched items and immediately updating filter counts to strictly the search results.
  - If checked: Toggling search results adds to or modifies active selections without unchecking non-matching items outside the search.
- **`(Select All)` Checkbox When Search is Empty:** When the search input is empty, display a master `(Select All)` checkbox showing the total available items in scope, automatically checking when all items are selected and unchecking if any item is deselected.
- **Pure Master Checkbox Bulk Selection (Exact Excel AutoFilter Mechanics):** Selection and deselection across all items or search results are driven purely and exclusively via the master checkboxes without push buttons inside dropdowns. Clicking `(Select All)` toggles all available options; clicking `(Select All Search Results)` toggles all matching items.
- **Independent Filter State Isolation:** Master checkboxes and search toggles within an individual dropdown must operate strictly and exclusively on that dropdown's options, and must never reset, clear, or invalidate selections made in any other filter. Global reset across all filters is exclusively reserved for the dedicated "Reset All Filters" action button.
- **Persistent User Choice Memory:** Retain checked/unchecked user choices across upstream filter toggles and search queries without losing state.
- **Dynamic & Distinct Options:** Populate dropdown checkbox options dynamically from actual available source data, using distinct, valid values.
- **Contextual Discovery:** Identify important business dimensions that meaningfully segment the summary, such as DISCOM, zone, circle, division, subdivision, consumer category, supply type, application status, connection status, date range, vendor, or scheme.
- **Cascading Dependencies:** Where appropriate, dynamically update dependent downstream checkbox options based on upstream checkbox selections (e.g. checking specific DISCOMs filters the available zones and divisions in subsequent dropdowns).
- **Consistent Filter Propagation:** Apply the set of checked values consistently across summaries, charts, KPI cards, detailed record lists, and downloaded CSV/Excel files.
- **Retention on Click:** Ensure that clicking any summary value retains the active combination of checked filters and opens/downloads only the records matching those checked criteria.
- **Safe Value Handling:** Safely handle null, blank, duplicate, and unexpected source values without throwing errors.
- **Mandatory acceptance criterion:** The summary, its clickable details, and its downloaded file must always reflect the exact set of active checkbox selections made in the dropdown filters, supporting full Excel-style search-and-select ergonomics.

### 8. Indian Number Formatting
Use the Indian numbering system for displaying all numerical values throughout the application, including summaries, KPI cards, tables, charts, tooltips, reports, downloadable presentation summaries, and other user-facing outputs.
- Use Indian comma grouping for whole numbers: `1,000`, `10,000`, `1,00,000`, `10,00,000`, and `1,00,000,000`.
- Apply the same convention consistently to currency amounts, consumer counts, application counts, energy values, and other applicable numerical quantities.
- Use the appropriate precision and decimal places for the data type.
- Keep the underlying numeric values unchanged. Formatting must not convert numbers into strings in a way that breaks calculations, sorting, filtering, aggregation, or exports.
- Apply formatting through reusable, centralized utility functions rather than implementing separate formatting logic in individual components.
- Use locale-aware formatting, such as `en-IN` where supported by the technology stack.
- **Mandatory acceptance criterion:** Every user-facing numerical display follows Indian comma grouping consistently, without affecting calculations or data integrity.

### 9. Avoid Hard-Coding and Build Generalized, Configurable Solutions
Avoid hard-coding business rules, data values, filters, labels, status mappings, column names, file paths, API endpoints, database connection details, thresholds, or project-specific assumptions directly into application logic.
- Build reusable, modular, configuration-driven code that can accommodate future changes with minimal code modifications.
- Keep business rules, status mappings, configurable thresholds, display labels, column mappings, and other changeable settings in appropriate configuration files, environment variables, database tables, or administrative settings.
- Discover and validate source-data schemas wherever feasible rather than assuming fixed column positions or inflexible source formats.
- Use parameterized database queries and secure configuration management. Never hard-code passwords, API keys, tokens, or other secrets.
- Create reusable components, services, utility functions, and shared modules for common functionality.
- Avoid duplicating logic across pages, reports, dashboards, or projects. Reuse existing components and services when appropriate.
- Design for variations in source columns, new categories, additional filters, changed business rules, increased data volumes, and future integrations.
- Use explicit configuration and validation when automatic schema discovery would be unsafe or ambiguous.
- Maintain backward compatibility where feasible and avoid unnecessary changes to unrelated functionality.
- Do not over-engineer. Generalization must improve maintainability, reliability, and change accommodation without compromising readability or performance.
- **Mandatory acceptance criterion:** A reasonable change in business rules, source columns, categories, thresholds, or configuration should not require rewriting multiple unrelated code modules.

### 10. Validation, Testing, and Regression Prevention
Apply the following checks whenever implementing or modifying a summary, dashboard, report, filter, or data-processing module:
1. Verify that summary aggregation is consistent with the source data.
2. Verify exact count parity between every clickable summary count and its corresponding detail file.
3. Verify that all active filters are applied consistently across summaries, charts, detail views, and exports.
4. Verify Indian number formatting across all user-facing numerical displays.
5. Test empty datasets, null values, duplicate records, unexpected categories, and boundary cases.
6. Check that changes do not break existing features or unrelated modules.
7. Log validation failures with sufficient diagnostic information to support troubleshooting.
8. Add or update automated tests for important business rules and data reconciliation logic.

### 11. Mandatory Working Procedure & Scope/Priority
Before modifying any project:
- Inspect the existing project structure, `global.md`, relevant source code, data schema, existing configurations, and current business logic.
- Reuse existing architecture and utilities where suitable.
- Identify all affected modules and potential regression risks before making changes.

After implementation:
- Run the available automated tests and relevant validation checks.
- Verify summary-to-detail reconciliation using actual test data or representative source data.
- Confirm that filters and exports behave consistently.
- Report the files modified, the rules implemented, the tests performed, and any unresolved issues.

Scope and Priority:
These standards are global and apply across all projects unless a project-specific requirement explicitly conflicts with a rule. Where a conflict exists, identify it and document the exception rather than silently ignoring the global standard.
Update `global.md` as the persistent source of these standards, and apply them to subsequent development work. Inspect existing projects for violations when they are next modified; do not claim that all existing projects have been updated or validated unless that work has actually been completed.
