# Retail Analytics — Agile Project Plan

## 1. Project purpose

The team will use the supplied retail datasets and the Jupyter Notebook to investigate where profit may be leaking, identify factors associated with reduced profitability, and produce evidence-based business recommendations.

**Main research question:** Where is profit leaking in the retail business, and which factors are associated with reduced profitability?

## 2. Proposed sprint goal

**Sprint goal statement**

> By the end of this proposed two-week sprint, the team will validate and analyse the five supplied retail datasets, complete the currency-aware profitability investigation, identify and explain the main evidence-supported profit risks, and publish a reproducible Jupyter Notebook, five evidence-based recommendations, a project README and a reviewed project report.

The two-week duration is a planning proposal; the team should replace it with the dates agreed by all members.

### Definition of Done

A task is complete when:

- Its output is saved in the agreed project folder or GitHub repository.
- The relevant notebook cells run without unresolved errors.
- Findings are supported by a table, chart or statistical result.
- Currency, missing-data and join limitations are documented where relevant.
- Another team member has reviewed the work.
- Changes are committed to the contributor's branch and submitted through a pull request where appropriate.

## 3. Project plan and work breakdown

| ID | Task | Description / acceptance criteria | Owner | Proposed priority |
|---|---|---|---|---|
| T1 | Confirm project scope | Confirm research question, deliverables, sprint dates and team responsibilities. | Michael + Teammate | High |
| T2 | Repository and folder check | Confirm `Data`, `outputs`, notebook and README are organised in the shared repository. | Michael | High |
| T3 | Dataset inventory | Confirm all five CSV files load and record their row/column counts. | Teammate | High |
| T4 | Data quality checks | Review missing values, duplicates, data types and ID relationships. Record issues. | Teammate | High |
| T5 | Currency and financial validation | Keep currencies separate; investigate sales-versus-item financial differences. | Michael | High |
| T6 | Safe table integration | Validate order IDs and prevent row multiplication when combining order and item data. | Michael + Teammate | High |
| T7 | Exploratory analysis | Complete sales, customer, geography, product and channel summaries. | Michael | High |
| T8 | Profit-leakage analysis | Review negative-profit orders/items, discounts, returns and delivery indicators. | Michael | High |
| T9 | Statistical analysis | Run appropriate tests, record group sizes, statistics, p-values and limitations. | Michael | Medium |
| T10 | Evidence-based recommendations | Write five recommendations and link each to a specific finding and measurable action. | Michael + Teammate | High |
| T11 | Visualisation and report review | Check chart titles, labels, currency units, interpretations and privacy. | Teammate | Medium |
| T12 | README preparation | Explain project purpose, data, setup, workflow, findings, limitations and how to run the notebook. | Michael | High |
| T13 | Final quality assurance | Restart kernel and run all notebook cells; check outputs and file paths. | Michael + Teammate | High |
| T14 | GitHub integration | Commit, push, review pull request and merge approved work into `main`. | Michael + Teammate | High |
| T15 | Sprint retrospective | Record what went well, what did not, lessons and actions after completion. | Michael + Teammate | Medium |

**Owner note:** “Michael” refers to the current contributor working on Michael's branch. “Teammate” is intentionally a role label because the teammate's name was not provided for this project. Replace it with the teammate's name before submission.

## 4. Kanban board

Use the board below as the team's starting board. Move cards as work progresses and keep only actively worked tasks in **In Progress**.

| Backlog / To Do | In Progress | Review / Testing | Done / Existing evidence |
|---|---|---|---|
| Finalise README and project plan (T12) — Michael | Verify remaining notebook outputs and data-loading paths (T3–T9) — Michael + Teammate | Review five recommendations against notebook evidence (T10) — Teammate | Five datasets have been loaded in the notebook (T3) |
| Complete report and presentation (T11) — Teammate | Validate currency and financial reconciliation notes (T5–T6) — Michael | Review visualisations and interpretation (T11) — Teammate | Notebook contains EDA, discount, returns, delivery, channel and statistical-analysis sections |
| Complete retrospective after sprint (T15) — Both | Finalise evidence-to-recommendation links (T10) — Both | Run notebook from a fresh kernel (T13) — Both | Repository has a shared `main` branch and the notebook/data files are present |
| Confirm sprint dates and teammate name (T1) — Both |  | Review pull request before merge (T14) — Both |  |

**Board rule:** Do not mark a task Done only because code exists. Confirm that it has run, the output has been checked, and the result has been reviewed.

## 5. Two project risks and mitigation actions

| Risk | Likelihood / impact | Mitigation action | Owner |
|---|---|---|---|
| Incorrect financial conclusions because the datasets contain multiple currencies, missing return-status values or inconsistent sales/item-level totals. | High / High | Analyse each currency separately; validate order IDs and joins; reconcile sales and item totals; treat missing return status as unknown; document unresolved differences. | Michael + Teammate |
| Team members overwrite work or introduce incompatible notebook/data changes during GitHub collaboration. | Medium / High | Use separate branches; pull the latest `main` before starting; make small commits; avoid editing the same notebook section simultaneously; review pull requests and resolve conflicts before merging. | Michael + Teammate |

## 6. Team communication and GitHub workflow

1. Agree on the task owner before work starts.
2. Update the Kanban board when a task changes status.
3. Work on a personal branch rather than editing `main` directly.
4. Pull the latest `main` before beginning a new work session.
5. Commit changes with clear messages and push to the contributor's branch.
6. Open a pull request with a short description of the change.
7. Ask the other team member to review the change.
8. Merge into `main` only after review and checks.
9. If a conflict occurs, coordinate with the other contributor before resolving it; do not discard someone else's work.

## 7. Sprint review checklist

- [ ] All five datasets load from the documented folder structure.
- [ ] Data quality issues and table relationships are documented.
- [ ] Currency-specific analysis is preserved; unlike currencies are not added together.
- [ ] Joins do not unintentionally duplicate order-level values.
- [ ] Discount, negative-profit, returns, delivery and channel analyses have been reviewed.
- [ ] Statistical tests include appropriate interpretation and limitations.
- [ ] Five recommendations are linked to evidence and measurable actions.
- [ ] README and project documentation are included in the repository.
- [ ] Notebook runs from a fresh kernel.
- [ ] Team changes have been reviewed and integrated into `main`.

## 8. Sprint retrospective

**Complete this section after the sprint/project work is finished. Do not fill it with assumed outcomes.**

**Sprint dates:** [Start date] to [End date]

**Participants:** [Names]

### What went well?
- [Record practices or tasks that worked well, with examples.]

### What did not go well?
- [Record delays, technical issues, communication problems or rework.]

### What did the team learn?
- [Record lessons about data quality, analysis, collaboration and GitHub.]

### What should the team improve next time?
- [Record specific process improvements.]

### Action items

| Improvement action | Owner | Due date | Status |
|---|---|---|---|
| [Action 1] | [Name] | [Date] | [To Do / In Progress / Done] |
| [Action 2] | [Name] | [Date] | [To Do / In Progress / Done] |
| [Action 3] | [Name] | [Date] | [To Do / In Progress / Done] |

## 9. Project deliverables

1. `README.md` — project overview, datasets, instructions, evidence-based recommendations and limitations.
2. `Retail_Analytics_Updated_Full_Notebook.ipynb` — analysis and outputs.
3. `PROJECT_PLAN.md` — project plan, sprint goal, Kanban board, task owners, risks and retrospective.
4. `outputs/` — reviewed charts, tables and final report materials.
5. Completed retrospective — added after the sprint is complete.
