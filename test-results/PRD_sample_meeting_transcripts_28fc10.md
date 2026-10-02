<!-- Source file: sample_meeting_transcripts.txt | Route: COMPLETE -->

# PRD: Reports and Dashboard Auto-Refresh

## 1. Overview
Not specified in source. See Open Questions.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- enterprise customers
- finance team
- users

## 4. Feature List
- R1: Users should be able to filter reports by date range, category, and status.
- R3: We need the dashboard to auto-refresh every 5 seconds so users always see the latest data.
- R5: Users need to export reports as PDF and CSV.

## 5. Acceptance Criteria
- For the PDF export, it must include the company logo at the top of every page.
- For CSV, it must preserve formulas - so if a cell has a SUM formula, the CSV should export the formula, not just the value.

## 6. Non-Functional Requirements
- R2: Results must load in under 2 seconds.
- R4: Performance is critical. We need to minimize API calls. Our infrastructure can't handle that load.

## 7. Stakeholders and Deadlines
Stakeholders:
- Sarah, PM (Wants reporting feature with date range, category, and status filters on a new dedicated page matching the existing design system, with results loading in under 2 seconds.)
- Raj, Engineering Lead (Concerned about performance with large datasets, backend ownership, and whether to query live or use a pre-computed data warehouse.)
- Lisa, Design (Inquired whether reporting is a new page or added to the existing dashboard, with designs needed by the end of April.)
- Tom, VP Product (Wants to add AI to reports to make them smarter like Competitor X.)
- Ananya, PM (Wants to scope AI feature requirements regarding data analyzed and expected outputs, and manages the export feature requirements.)
- Mike, Engineering (Concerned that a 5-second auto-refresh generates a lot of API calls hitting the backend, suggesting WebSockets as an alternative.)
- Priya, PM (Wants the dashboard to auto-refresh every 5 seconds to provide real-time data and address stale data complaints.)
- Kevin, DevOps (Strongly disagrees with 5-second refresh due to infrastructure load and potential outages, emphasizing minimizing API calls.)

Deadlines:
- end of Q3
- end of April

## 8. Dependencies and Risks
Dependencies:
- Lisa's designs (Owner: Lisa, ETA: known)

Risks and Conflicts:
- Priya: We need the dashboard to auto-refresh every 5 seconds so users always see the latest data. vs Kevin: We need to minimize API calls. Our infrastructure can't handle that load. (Needs stakeholder resolution)

## 9. Assumptions
Unconfirmed:
- The data source decision will be made after reviewing Lisa's designs and query patterns.
- Export to CSV will use XLSX instead of plain CSV to support formula preservation while keeping the user-facing label as Export to CSV.

## 10. Open Questions
- Ambiguity (AI feature): Tom wants to add AI to reports like Competitor X without specifying data to analyze or expected outputs.
- Ambiguity (Real-time updates): Mentioned in general discussion notes without specific implementation details.
- Ambiguity (Reporting feature): Data source is TBD, pending query patterns and Lisa's designs.
- Contradiction: Priya: We need the dashboard to auto-refresh every 5 seconds so users always see the latest data. vs Kevin: We need to minimize API calls. Our infrastructure can't handle that load. (Needs stakeholder resolution)
- Which categories exist for report filtering
- Which statuses exist for report filtering
- What specific reporting features or AI capabilities Competitor X has
- What data the AI should analyze for the reporting feature
- What specific outputs are expected from the AI reporting feature
- What the exact budget amount is for the project
- Which specific analytics team members need to be consulted
- Which specific designer is assigned to follow up on design
- What real-time means in the context of the dashboard updates

---

# Epics, Features and User Stories

## E1: Reports and Dashboard
Epic covering report filtering, dashboard refreshing, and report exporting.

### F1: Report Filtering and Dashboard Refreshing

**US1**: As a users, I want to filter reports by date range, category, and status.
- Priority: Must Have (Stated as a functional requirement without any explicit priority words indicating optionality.)
- Source requirements: R1
- Linked NFRs: R2
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on filtering capabilities, performance NFR under 2 seconds, and multiple open questions regarding categories, statuses, and data sources pending query patterns and designs.
- FLAG, underspecified: Which categories exist for report filtering

**US2**: As a users, I want the dashboard to auto-refresh every 5 seconds so users always see the latest data.
- Priority: Must Have (Stated as a functional requirement without any explicit priority words indicating optionality.)
- Source requirements: R3
- Linked NFRs: R4
- Acceptance criteria: None stated in source
- Size (provisional): L. Provisional size due to conflicting requirements between auto-refresh frequency and infrastructure load limits, along with open questions regarding real-time implementation details.
- FLAG, underspecified: Contradiction: Priya: We need the dashboard to auto-refresh every 5 seconds so users always see the latest data. vs Kevin: We need to minimize API calls. Our infrastructure can't handle that load. (Needs stakeholder resolution)

**US3**: As a users, I want to export reports as PDF and CSV.
- Priority: Must Have (Stated as a functional requirement without any explicit priority words indicating optionality.)
- Source requirements: R5
- Linked NFRs: None
- Acceptance criteria: For the PDF export, it must include the company logo at the top of every page.; For CSV, it must preserve formulas - so if a cell has a SUM formula, the CSV should export the formula, not just the value.
- Size (provisional): M. Provisional size based on dual export formats (PDF and CSV) with specific formatting rules including company logos on every page and formula preservation.

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which categories and statuses should be available for report filtering?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: Which categories exist for report filtering

Q2. What is the agreed-upon data source or query pattern for the reporting feature?
   - Ask: Raj
   - Blocking: Yes
   - Grounded in: Reporting feature: Data source is TBD, pending query patterns and Lisa's designs.

Q3. How should the requirement for a 5-second dashboard auto-refresh be reconciled with infrastructure limitations regarding API calls?
   - Ask: Priya
   - Blocking: Yes
   - Grounded in: Contradiction: Priya: We need the dashboard to auto-refresh every 5 seconds so users always see the latest data. vs Kevin: We need to minimize API calls. Our infrastructure can't handle that load.

Q4. What specific implementation details or expectations define real-time updates for the dashboard?
   - Ask: Priya
   - Blocking: No
   - Grounded in: Real-time updates: Mentioned in general discussion notes without specific implementation details.

Q5. What specific data should the AI feature analyze and what are the expected outputs?
   - Ask: Tom
   - Blocking: No
   - Grounded in: AI feature: Tom wants to add AI to reports like Competitor X without specifying data to analyze or expected outputs.
