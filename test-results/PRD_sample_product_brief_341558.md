<!-- Source file: sample_product_brief.txt | Route: COMPLETE -->

# PRD: Analytics Dashboard

## 1. Overview
Building an analytics dashboard that gives business users visibility into key metrics without needing to write SQL queries or ask the data team.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- Business analysts who currently export data to Excel
- Team leads who need weekly performance summaries
- Executives who want a high-level overview without digging into details

## 4. Feature List
- R1: Dashboard should display 5 core metrics: revenue, active users, churn rate, NPS score, and support ticket volume
- R2: Users should be able to filter by date range (last 7 days, 30 days, 90 days, custom)
- R4: Must support role-based access: executives see all data, team leads see their team only
- R5: Export to PDF for monthly board reports

## 5. Acceptance Criteria
Not specified in source. See Open Questions.

## 6. Non-Functional Requirements
- R3: Data should refresh every 15 minutes (not real-time, to manage cost)
- R6: Must integrate with our existing PostgreSQL data warehouse
- R7: Cannot use any third-party analytics tools (licensing cost concern)
- R8: Must be accessible on mobile (responsive design)
- R9: Target launch: Q3 2026

## 7. Stakeholders and Deadlines
- Priya Sharma, Product Manager
- Deadline: Q3 2026

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- analytics dashboard: The dashboard layout, visualization types, and interactivity are not defined.
- custom date range: The bounds and UI mechanism for custom date ranges are not specified.
- team leads see their team only: How a team is defined and mapped in the data warehouse is unspecified.
- Which dashboard layout and visualization components should be used
- What specific date formats and calendar picker rules are required for custom date ranges
- How teams are structured and mapped in the PostgreSQL data warehouse for role-based access
- What formatting, styling, and branding are required for the PDF export

---

# Epics, Features and User Stories

## E1: Analytics Dashboard Core Capabilities
Core dashboard metrics, filtering, role-based access, and reporting capabilities for stakeholders.

### F1: Dashboard Metrics and Filtering

**US1**: As a Business analysts who currently export data to Excel, I want Dashboard should display 5 core metrics: revenue, active users, churn rate, NPS score, and support ticket volume
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R1
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on integration with PostgreSQL data warehouse, 15-minute data refresh requirement, responsive design constraint, and lack of layout/visualization definitions.
- FLAG, underspecified: Which dashboard layout and visualization components should be used

**US2**: As a Business analysts who currently export data to Excel, I want Users should be able to filter by date range (last 7 days, 30 days, 90 days, custom)
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R2
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size due to date range filtering requirements, PostgreSQL data warehouse integration, and unspecified custom date range rules.
- FLAG, underspecified: What specific date formats and calendar picker rules are required for custom date ranges

**US3**: As a Team leads who need weekly performance summaries, I want Dashboard should display 5 core metrics: revenue, active users, churn rate, NPS score, and support ticket volume
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R1
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on 5 core metrics display, PostgreSQL data warehouse integration, refresh NFR, and undefined visualization components.
- FLAG, underspecified: Which dashboard layout and visualization components should be used

**US4**: As a Team leads who need weekly performance summaries, I want Users should be able to filter by date range (last 7 days, 30 days, 90 days, custom)
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R2
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on date filtering capabilities, PostgreSQL data warehouse integration, and undefined custom date range UI mechanisms.
- FLAG, underspecified: What specific date formats and calendar picker rules are required for custom date ranges

**US5**: As a Executives who want a high-level overview without digging into details, I want Dashboard should display 5 core metrics: revenue, active users, churn rate, NPS score, and support ticket volume
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R1
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size reflecting executive overview metrics display, PostgreSQL data warehouse integration, and undefined visualization layouts.
- FLAG, underspecified: Which dashboard layout and visualization components should be used

**US6**: As a Executives who want a high-level overview without digging into details, I want Users should be able to filter by date range (last 7 days, 30 days, 90 days, custom)
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R2
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for date range filtering targeted at executives, requiring PostgreSQL integration and unresolved custom date range criteria.
- FLAG, underspecified: What specific date formats and calendar picker rules are required for custom date ranges

### F2: Access Control and Reporting

**US7**: As a Business analysts who currently export data to Excel, I want Must support role-based access: executives see all data, team leads see their team only
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R4
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size driven by role-based access control requirements mapped against a PostgreSQL data warehouse where team mapping is currently unspecified.
- FLAG, underspecified: How teams are structured and mapped in the PostgreSQL data warehouse for role-based access

**US8**: As a Business analysts who currently export data to Excel, I want Export to PDF for monthly board reports
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R5
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on PDF export functionality for board reports, coupled with underlying PostgreSQL data warehouse integration and responsive design constraints.
- FLAG, underspecified: What formatting, styling, and branding are required for the PDF export

**US9**: As a Team leads who need weekly performance summaries, I want Must support role-based access: executives see all data, team leads see their team only
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R4
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for team lead role-based access controls interacting with the PostgreSQL data warehouse with unspecified team mapping.
- FLAG, underspecified: How teams are structured and mapped in the PostgreSQL data warehouse for role-based access

**US10**: As a Team leads who need weekly performance summaries, I want Export to PDF for monthly board reports
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R5
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for PDF export feature requested by team leads, utilizing PostgreSQL data warehouse integration without specified branding or styling rules.
- FLAG, underspecified: What formatting, styling, and branding are required for the PDF export

**US11**: As a Executives who want a high-level overview without digging into details, I want Must support role-based access: executives see all data, team leads see their team only
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R4
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for executive role-based access implementation tied to PostgreSQL data warehouse architecture with open data mapping questions.
- FLAG, underspecified: How teams are structured and mapped in the PostgreSQL data warehouse for role-based access

**US12**: As a Executives who want a high-level overview without digging into details, I want Export to PDF for monthly board reports
- Priority: Must Have (Stated functional requirement with no explicit alternative priority term in the source.)
- Source requirements: R5
- Linked NFRs: R3, R6, R7, R8
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for executive PDF export capability requiring PostgreSQL data warehouse integration and missing formatting/branding criteria.
- FLAG, underspecified: What formatting, styling, and branding are required for the PDF export

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which dashboard layout and visualization components should be used to display the 5 core metrics?
   - Ask: Priya Sharma
   - Blocking: No
   - Grounded in: The dashboard layout, visualization types, and interactivity are not defined.

Q2. What specific date formats and calendar picker rules are required for custom date ranges?
   - Ask: Priya Sharma
   - Blocking: No
   - Grounded in: The bounds and UI mechanism for custom date ranges are not specified.

Q3. How are teams structured and mapped in the PostgreSQL data warehouse for role-based access?
   - Ask: Priya Sharma
   - Blocking: Yes
   - Grounded in: How a team is defined and mapped in the data warehouse is unspecified.

Q4. What formatting, styling, and branding are required for the PDF export?
   - Ask: Priya Sharma
   - Blocking: No
   - Grounded in: What formatting, styling, and branding are required for the PDF export
