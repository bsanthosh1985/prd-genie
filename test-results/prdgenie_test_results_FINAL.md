# PRD Genie baseline test results

Run 3 - with Pinecone RAG
Run date: 2026-10-02T19:35:05.335Z
Model: gemini-3.5-flash-lite
Passed: 12 / 12

| Test | Name | Route | Result | Checks | Failed checks |
|---|---|---|---|---|---|
| T1 | Detailed transcript | COMPLETE | PASS | 11 of 11 | - |
| T2 | Vague brief | INSUFFICIENT | PASS | 8 of 8 | - |
| T3 | Contradictory | COMPLETE | PASS | 6 of 6 | - |
| T4 | Feature request with acceptance criteria | COMPLETE | PASS | 9 of 9 | - |
| T5 | Incomplete notes | INSUFFICIENT | PASS | 9 of 9 | - |
| T6 | Multi-stakeholder | INSUFFICIENT | PASS | 9 of 9 | - |
| T7 | Technical requirements | COMPLETE | PASS | 7 of 7 | - |
| T8 | User persona heavy | COMPLETE | PASS | 9 of 9 | - |
| T9 | Empty/minimal | BLOCKED_BY_GUARD | PASS | 5 of 5 | - |
| T10 | Feature with dependencies | COMPLETE | PASS | 8 of 8 | - |
| T11 | PRD generation (from T1) | COMPLETE | PASS | 16 of 16 | - |
| T12 | Story breakdown (from T11) | COMPLETE | PASS | 6 of 6 | - |

Automated checks are keyword and structure tests. Items under "Manual review" need a human look.

---

## T1: Detailed transcript: PASS

**Input:** The user should be able to filter reports by date range, category, and status. Results must load in under 2 seconds. PM: Sarah. Deadline: Q3.

**Route:** COMPLETE  |  **Checks passed:** 11 of 11  |  **JSON repaired:** false

**Requirements extracted:** The user should be able to filter reports by date range, category, and status. | Results must load in under 2 seconds.

**Output:**

~~~markdown
# PRD: Report Filtering Feature

## 1. Overview
Not specified in source. See Open Questions.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- user

## 4. Feature List
- R1: The user should be able to filter reports by date range, category, and status.

## 5. Acceptance Criteria
Not specified in source. See Open Questions.

## 6. Non-Functional Requirements
- R2: Results must load in under 2 seconds.

## 7. Stakeholders and Deadlines
- Sarah (PM)
- Deadline: Q3

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- reports: The input mentions reports but does not define which reports or their structure.
- date range: The input mentions date range but does not define the format or allowable ranges.
- category: The input mentions category but does not list which categories exist.
- status: The input mentions status but does not list the possible status values.
- Results: The input mentions results but does not specify the format, pagination, or sorting.
- Which reports are available to be filtered
- What date range format and allowable limits apply
- Which categories exist
- What the possible status values are
- What specific results are expected and how they are displayed

---

# Epics, Features and User Stories

## E1: Report Filtering
Epic covering report filtering capabilities.

### F1: Filter Reports

**US1**: As a user, I want to filter reports by date range, category, and status
- Priority: Must Have (The source states a functional requirement without using any explicit priority words indicating optionality or lower priority.)
- Source requirements: R1
- Linked NFRs: R2
- Acceptance criteria: None stated in source
- Size (provisional): M. This size is provisional as the story contains multiple distinct capabilities (filtering by date range, category, and status) and a linked performance NFR, but lacks critical definitions.
- FLAG, underspecified: The input lacks definitions for reports, date range format, available categories, possible status values, and results format, which could materially change the effort.

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which reports and report structures are available to be filtered?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: reports: The input mentions reports but does not define which reports or their structure.

Q2. What is the required date range format and what are the allowable limits?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: date range: The input mentions date range but does not define the format or allowable ranges.

Q3. Which categories exist for filtering reports?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: category: The input mentions category but does not list which categories exist.

Q4. What are the possible status values that can be filtered?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: status: The input mentions status but does not list the possible status values.

Q5. What specific results are expected, and how should they be formatted, paginated, or sorted?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: Results: The input mentions results but does not specify the format, pagination, or sorting.

~~~

---

## T2: Vague brief: PASS

**Input:** We need better reporting. Something like what Competitor X has.

**Route:** INSUFFICIENT  |  **Checks passed:** 8 of 8  |  **JSON repaired:** false

**Output:**

~~~markdown
# No PRD generated

The input does not contain enough information to extract requirements.

## What is missing
- What specific reporting features are needed
- What specific features Competitor X has that should be replicated

## Ambiguous statements
- better reporting: It is a general wish that names no specific capability or feature.
- Competitor X: It references an external competitor without specifying which features or aspects to copy.

## Clarification questions
Readiness: Not ready

Q1. What data or metrics should the better reporting show?
   - Ask: Requester / Product Owner
   - Grounded in: better reporting

Q2. What output format should the better reporting take?
   - Ask: Requester / Product Owner
   - Grounded in: better reporting

Q3. Which users or audience is the better reporting for?
   - Ask: Requester / Product Owner
   - Grounded in: better reporting

Q4. Which specific features or aspects of Competitor X should be replicated?
   - Ask: Requester / Product Owner
   - Grounded in: Competitor X

~~~

---

## T3: Contradictory: PASS

**Input:** The dashboard should auto-refresh every 5 seconds. [Later in same meeting] Performance is critical, minimize API calls.

**Route:** COMPLETE  |  **Checks passed:** 6 of 6  |  **JSON repaired:** false

**Requirements extracted:** The dashboard should auto-refresh every 5 seconds. | Minimize API calls.

**Contradictions recorded:** The dashboard should auto-refresh every 5 seconds. <> Performance is critical, minimize API calls.

**Manual review:** Confirm the contradiction is flagged for stakeholder resolution and neither statement is dropped.

**Output:**

~~~markdown
# PRD: Dashboard Auto-Refresh and Performance
## 1. Overview
Not specified in source. See Open Questions.
## 2. Goals
Not specified in source. See Open Questions.
## 3. User Personas
Not specified in source. See Open Questions.
## 4. Feature List
- R1: The dashboard should auto-refresh every 5 seconds.
## 5. Acceptance Criteria
Not specified in source. See Open Questions.
## 6. Non-Functional Requirements
- R2: Minimize API calls.
## 7. Stakeholders and Deadlines
Not specified in source. See Open Questions.
## 8. Dependencies and Risks
- Statement A: "The dashboard should auto-refresh every 5 seconds." conflicts with Statement B: "Performance is critical, minimize API calls." Note: needs stakeholder resolution.
## 9. Assumptions
None stated in source.
## 10. Open Questions
- Performance is critical: It does not specify exact metrics or latency thresholds for what constitutes acceptable performance.
- Statement A: "The dashboard should auto-refresh every 5 seconds." conflicts with Statement B: "Performance is critical, minimize API calls." Note: needs stakeholder resolution.
- Which dashboard is being referred to
- What specific performance metrics or thresholds are required

---

# Epics, Features and User Stories

## E1: Dashboard Auto-Refresh and Performance
Epic covering dashboard auto-refresh and performance requirements.

### F1: Dashboard Refresh

**US1**: As a User, I want the dashboard to auto-refresh every 5 seconds
- Priority: Must Have (Classified as Must Have because it is a stated functional requirement without an explicit low-priority indicator.)
- Source requirements: R1
- Linked NFRs: R2
- Acceptance criteria: None stated in source
- Size (provisional): M. This size is provisional. The scope involves an auto-refresh functional requirement coupled with an NFR to minimize API calls, along with conflicting requirements and multiple open questions that require resolution.
- FLAG, underspecified: Performance is critical: It does not specify exact metrics or latency thresholds for what constitutes acceptable performance.

---

# Gap Analysis
Readiness: Needs clarification

Q1. What specific performance metrics or latency thresholds are required?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: Performance is critical

Q2. How should the requirement to auto-refresh every 5 seconds be reconciled with the requirement to minimize API calls for performance?
   - Ask: Requester / Product Owner
   - Blocking: Yes
   - Grounded in: The dashboard should auto-refresh every 5 seconds.

Q3. Which dashboard is being referred to?
   - Ask: Requester / Product Owner
   - Blocking: Yes
   - Grounded in: Which dashboard is being referred to

Q4. What specific performance metrics or thresholds are required?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: What specific performance metrics or thresholds are required

~~~

---

## T4: Feature request with acceptance criteria: PASS

**Input:** Users need to export reports as PDF and CSV. PDF must include company logo. CSV must preserve formulas.

**Route:** COMPLETE  |  **Checks passed:** 9 of 9  |  **JSON repaired:** false

**Requirements extracted:** Users need to export reports as PDF and CSV.

**Acceptance criteria extracted:** PDF must include company logo. | CSV must preserve formulas.

**Output:**

~~~markdown
# PRD: Export Reports

## 1. Overview
Users need to export reports as PDF and CSV.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- Users

## 4. Feature List
- R1: Users need to export reports as PDF and CSV.

## 5. Acceptance Criteria
- PDF must include company logo.
- CSV must preserve formulas.

## 6. Non-Functional Requirements
Not specified in source. See Open Questions.

## 7. Stakeholders and Deadlines
Not specified in source. See Open Questions.

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- item: reports, why_ambiguous: It is not specified which reports are to be exported.
- item: company logo, why_ambiguous: It is not specified which company logo image file or format must be used.
- item: formulas, why_ambiguous: It is not specified which formulas need to be preserved in the CSV.
- Which reports need to be exported
- Which company logo image file or format must be used for the PDF
- Which specific formulas must be preserved in the CSV

---

# Epics, Features and User Stories

## E1: Export Reports
Epic covering report export functionalities.

### F1: Report Exporting

**US1**: As a Users, I want to export reports as PDF and CSV
- Priority: Must Have (Stated as a functional requirement without any explicit optional or low priority keywords.)
- Source requirements: R1
- Linked NFRs: None
- Acceptance criteria: PDF must include company logo.; CSV must preserve formulas.
- Size (provisional): M. This is a provisional size based on multiple distinct capabilities (PDF export with logo and CSV export with formula preservation) and open questions.
- FLAG, underspecified: It is not specified which reports are to be exported, which company logo image file or format must be used, and which formulas need to be preserved in the CSV, which could materially change the effort.

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which specific reports need to be exported?
   - Ask: Requester / Product Owner
   - Blocking: Yes
   - Grounded in: It is not specified which reports are to be exported.

Q2. Which company logo image file or format must be used for the PDF export?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: It is not specified which company logo image file or format must be used.

Q3. Which specific formulas need to be preserved in the CSV export?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: It is not specified which formulas need to be preserved in the CSV.

~~~

---

## T5: Incomplete notes: PASS

**Input:** Discussed dashboard... John mentioned something about real-time... budget TBD...

**Route:** INSUFFICIENT  |  **Checks passed:** 9 of 9  |  **JSON repaired:** false

**Output:**

~~~markdown
# No PRD generated

The input does not contain enough information to extract requirements.

## What is missing
- Which dashboard is being discussed
- What real-time means in this context
- What the budget amount is

## Ambiguous statements
- dashboard: Mentioned without any details, specifications, or requirements.
- real-time: Mentioned by John without defining what real-time means or applies to.
- budget: Stated as TBD with no amount provided.

## Stakeholder viewpoints
- John: mentioned something about real-time

## Clarification questions
Readiness: Not ready

Q1. What data or metrics should the dashboard show?
   - Ask: John
   - Grounded in: dashboard

Q2. What output format should the dashboard take?
   - Ask: John
   - Grounded in: dashboard

Q3. Which users or audience is the dashboard for?
   - Ask: John
   - Grounded in: dashboard

Q4. What does real-time mean in this context?
   - Ask: John
   - Grounded in: real-time

Q5. What is the budget amount?
   - Ask: Requester / Product Owner
   - Grounded in: budget TBD

~~~

---

## T6: Multi-stakeholder: PASS

**Input:** Engineering wants microservices. Design wants single-page app. PM wants it shipped by March.

**Route:** INSUFFICIENT  |  **Checks passed:** 9 of 9  |  **JSON repaired:** false

**Contradictions recorded:** Engineering wants microservices. <> Design wants single-page app.

**Manual review:** Confirm all three viewpoints are captured neutrally and no side is favoured.

**Output:**

~~~markdown
# No PRD generated

The input does not contain enough information to extract requirements.

## What is missing
- Which microservices are to be built
- What frameworks or technologies are required for the single-page app
- Which specific date in March is the shipping deadline

## Ambiguous statements
- microservices: It is stated as a want by Engineering without any details on scope, services, or architecture.
- single-page app: It is stated as a want by Design without framework or functional specifications.
- shipped by March: The exact ship date, year, and criteria for shipping are not defined.

## Stakeholder viewpoints
- Engineering (Engineering): Engineering wants microservices.
- Design (Design): Design wants single-page app.
- PM (PM): PM wants it shipped by March.

## Tensions needing stakeholder resolution
- "Engineering wants microservices." vs "Design wants single-page app."

## Clarification questions
Readiness: Not ready

Q1. What specific services, scope, or architecture are intended by the microservices request?
   - Ask: Engineering
   - Grounded in: microservices

Q2. What framework, technologies, or functional specifications are required for the single-page app?
   - Ask: Design
   - Grounded in: single-page app

Q3. What is the exact target date and year for 'shipped by March', and what are the criteria for shipping?
   - Ask: PM
   - Grounded in: shipped by March

~~~

---

## T7: Technical requirements: PASS

**Input:** API must support 10,000 concurrent users. Response time < 200ms at p95. Must integrate with Salesforce REST API v52.

**Route:** COMPLETE  |  **Checks passed:** 7 of 7  |  **JSON repaired:** false

**Requirements extracted:** API must support 10,000 concurrent users. | Response time < 200ms at p95. | Must integrate with Salesforce REST API v52.

**Output:**

~~~markdown
# PRD: API and Salesforce REST API v52 Integration

## 1. Overview
Not specified in source. See Open Questions.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
Not specified in source. See Open Questions.

## 4. Feature List
Not specified in source. See Open Questions.

## 5. Acceptance Criteria
Not specified in source. See Open Questions.

## 6. Non-Functional Requirements
- R1: API must support 10,000 concurrent users.
- R2: Response time < 200ms at p95.
- R3: Must integrate with Salesforce REST API v52.

## 7. Stakeholders and Deadlines
Not specified in source. See Open Questions.

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- What specific endpoints or data operations are required for the Salesforce REST API v52 integration

---

# Epics, Features and User Stories

## E1: API and Salesforce REST API v52 Integration
Epic covering non-functional requirements and integration specifications for the API and Salesforce.

### F1: API Performance and Integration

**US1**: As a User, I want API must support 10,000 concurrent users
- Priority: Must Have (Stated as a functional requirement without explicit priority words like 'nice to have' or 'optional'.)
- Source requirements: R1
- Linked NFRs: R1
- Acceptance criteria: None stated in source
- Size (provisional): S. This size is provisional as it involves a single linked NFR (R1) for concurrent users without additional open questions.

**US2**: As a User, I want Response time < 200ms at p95
- Priority: Must Have (Stated as a functional requirement without explicit priority words like 'nice to have' or 'optional'.)
- Source requirements: R2
- Linked NFRs: R2
- Acceptance criteria: None stated in source
- Size (provisional): S. This size is provisional as it involves a single linked NFR (R2) for response time without additional open questions.

**US3**: As a User, I want Must integrate with Salesforce REST API v52
- Priority: Must Have (Stated as a functional requirement without explicit priority words like 'nice to have' or 'optional'.)
- Source requirements: R3
- Linked NFRs: R3
- Acceptance criteria: None stated in source
- Size (provisional): M. This size is provisional due to the integration requirement with Salesforce REST API v52 and an open question regarding specific endpoints.
- FLAG, underspecified: What specific endpoints or data operations are required for the Salesforce REST API v52 integration

---

# Gap Analysis
Readiness: Needs clarification

Q1. What specific endpoints or data operations are required for the Salesforce REST API v52 integration?
   - Ask: Requester / Product Owner
   - Blocking: Yes
   - Grounded in: What specific endpoints or data operations are required for the Salesforce REST API v52 integration

~~~

---

## T8: User persona heavy: PASS

**Input:** Admins need bulk user management. End users need a simplified view. Auditors need read-only access with full history.

**Route:** COMPLETE  |  **Checks passed:** 9 of 9  |  **JSON repaired:** false

**Requirements extracted:** Admins need bulk user management. | End users need a simplified view. | Auditors need read-only access with full history.

**Output:**

~~~markdown
# PRD: Bulk User Management, Simplified View, and Audit History

## 1. Overview
Admins need bulk user management, end users need a simplified view, and auditors need read-only access with full history.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- Admins (Role: Admins) - Viewpoint: Admins need bulk user management.
- End users (Role: End users) - Viewpoint: End users need a simplified view.
- Auditors (Role: Auditors) - Viewpoint: Auditors need read-only access with full history.

## 4. Feature List
- R1: Admins need bulk user management.
- R2: End users need a simplified view.
- R3: Auditors need read-only access with full history.

## 5. Acceptance Criteria
Not specified in source. See Open Questions.

## 6. Non-Functional Requirements
Not specified in source. See Open Questions.

## 7. Stakeholders and Deadlines
Stakeholders:
- Admins (Role: Admins)
- End users (Role: End users)
- Auditors (Role: Auditors)

Deadlines:
Not specified in source. See Open Questions.

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- Item: bulk user management - Why ambiguous: It does not specify what actions are included in bulk user management.
- Item: simplified view - Why ambiguous: It does not define what information or elements are included in or excluded from the simplified view.
- Item: full history - Why ambiguous: It does not specify the time range or types of events included in the full history.
- What specific operations are included in bulk user management
- What specific elements or data are included in the simplified view
- What specific events and time range constitute full history for auditors

---

# Epics, Features and User Stories

## E1: User Management, Views, and Audit History
Epic covering bulk user management for admins, simplified view for end users, and read-only access with full history for auditors.

### F1: User Management and Access Views

**US1**: As a Admins, I want bulk user management
- Priority: Must Have (Stated as a functional requirement without an explicit priority word indicating it is optional.)
- Source requirements: R1
- Linked NFRs: None
- Acceptance criteria: None stated in source
- Size (provisional): M. All sizes are provisional. Complexity is driven by the bulk user management capability requested by admins.
- FLAG, underspecified: What specific operations are included in bulk user management

**US2**: As a End users, I want a simplified view
- Priority: Must Have (Stated as a functional requirement without an explicit priority word indicating it is optional.)
- Source requirements: R2
- Linked NFRs: None
- Acceptance criteria: None stated in source
- Size (provisional): S. All sizes is provisional. Scope involves providing a simplified view for end users.
- FLAG, underspecified: What specific elements or data are included in the simplified view

**US3**: As a Auditors, I want read-only access with full history
- Priority: Must Have (Stated as a functional requirement without an explicit priority word indicating it is optional.)
- Source requirements: R3
- Linked NFRs: None
- Acceptance criteria: None stated in source
- Size (provisional): M. All sizes are provisional. Scope includes read-only access combined with full history tracking for auditors.
- FLAG, underspecified: What specific events and time range constitute full history for auditors

---

# Gap Analysis
Readiness: Needs c
...[truncated]
~~~

---

## T9: Empty/minimal: PASS

**Input:** Meeting happened. Notes: none.

**Route:** BLOCKED_BY_GUARD  |  **Checks passed:** 5 of 5  |  **JSON repaired:** false

**Output:**

~~~markdown
No requirements can be extracted from this input. No PRD generated
~~~

---

## T10: Feature with dependencies: PASS

**Input:** SSO login requires the new auth service which is being built by Team Alpha. ETA unknown.

**Route:** COMPLETE  |  **Checks passed:** 8 of 8  |  **JSON repaired:** false

**Requirements extracted:** SSO login requires the new auth service

**Manual review:** Confirm the unknown ETA is flagged as a risk.

**Output:**

~~~markdown
# PRD: SSO Login and New Auth Service
## 1. Overview
SSO login requires the new auth service.
## 2. Goals
Not specified in source. See Open Questions.
## 3. User Personas
Not specified in source. See Open Questions.
## 4. Feature List
- R1: SSO login requires the new auth service
## 5. Acceptance Criteria
Not specified in source. See Open Questions.
## 6. Non-Functional Requirements
Not specified in source. See Open Questions.
## 7. Stakeholders and Deadlines
Not specified in source. See Open Questions.
## 8. Dependencies and Risks
- Item: new auth service, Owner: Team Alpha, ETA: unknown
- Risk: The ETA for the new auth service (owner: Team Alpha) is unknown and is a schedule risk for the feature that depends on it.
## 9. Assumptions
None stated in source.
## 10. Open Questions
- Item: SSO login. Why ambiguous: The input mentions SSO login without defining which identity providers are supported or what authentication protocol should be used.
- Item: new auth service. Why ambiguous: The input mentions the new auth service without specifying its technical specifications, APIs, or integration requirements.
- Which identity providers or authentication protocols are supported for SSO login
- What technical specifications, APIs, or integration requirements apply to the new auth service
- ETA for new auth service (owner: Team Alpha) is unknown

---

# Epics, Features and User Stories

## E1: SSO Login and Authentication
Epics related to SSO login and integration with the new auth service.

### F1: SSO Authentication

**US1**: As a User, I want SSO login using the new auth service
- Priority: Must Have (The source states a functional requirement without any explicit priority word, so it defaults to Must Have.)
- Source requirements: R1
- Linked NFRs: None
- Acceptance criteria: None stated in source
- Size (provisional): L. This size is provisional. The story involves integration with an external dependency (the new auth service) with an unknown ETA and unspecified identity providers or protocols.
- FLAG, underspecified: ETA for new auth service (owner: Team Alpha) is unknown, and which identity providers or authentication protocols are supported for SSO login is missing.

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which identity providers or authentication protocols are supported for SSO login?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: SSO login

Q2. What technical specifications, APIs, or integration requirements apply to the new auth service?
   - Ask: Requester / Product Owner
   - Blocking: Yes
   - Grounded in: new auth service

Q3. What is the expected ETA for the new auth service owned by Team Alpha?
   - Ask: Team Alpha
   - Blocking: Yes
   - Grounded in: Item: new auth service, Owner: Team Alpha, ETA: unknown

~~~

---

## T11: PRD generation (from T1): PASS

**Input:** (derived from T1 output)

**Route:** COMPLETE  |  **Checks passed:** 16 of 16  |  **JSON repaired:** false

**Requirements extracted:** The user should be able to filter reports by date range, category, and status. | Results must load in under 2 seconds.

**Manual review:** Skim the PRD for any content not in T1.

**Output:**

~~~markdown
# PRD: Report Filtering Feature

## 1. Overview
Not specified in source. See Open Questions.

## 2. Goals
Not specified in source. See Open Questions.

## 3. User Personas
- user

## 4. Feature List
- R1: The user should be able to filter reports by date range, category, and status.

## 5. Acceptance Criteria
Not specified in source. See Open Questions.

## 6. Non-Functional Requirements
- R2: Results must load in under 2 seconds.

## 7. Stakeholders and Deadlines
- Sarah (PM)
- Deadline: Q3

## 8. Dependencies and Risks
Not specified in source. See Open Questions.

## 9. Assumptions
None stated in source.

## 10. Open Questions
- reports: The input mentions reports but does not define which reports or their structure.
- date range: The input mentions date range but does not define the format or allowable ranges.
- category: The input mentions category but does not list which categories exist.
- status: The input mentions status but does not list the possible status values.
- Results: The input mentions results but does not specify the format, pagination, or sorting.
- Which reports are available to be filtered
- What date range format and allowable limits apply
- Which categories exist
- What the possible status values are
- What specific results are expected and how they are displayed
~~~

---

## T12: Story breakdown (from T11): PASS

**Input:** (derived from T1 output)

**Route:** COMPLETE  |  **Checks passed:** 6 of 6  |  **JSON repaired:** false

**Requirements extracted:** The user should be able to filter reports by date range, category, and status. | Results must load in under 2 seconds.

**Manual review:** Confirm the priorities are sensible.

**Output:**

~~~markdown
# Epics, Features and User Stories

## E1: Report Filtering
Epic covering report filtering capabilities.

### F1: Filter Reports

**US1**: As a user, I want to filter reports by date range, category, and status
- Priority: Must Have (The source states a functional requirement without using any explicit priority words indicating optionality or lower priority.)
- Source requirements: R1
- Linked NFRs: R2
- Acceptance criteria: None stated in source
- Size (provisional): M. This size is provisional as the story contains multiple distinct capabilities (filtering by date range, category, and status) and a linked performance NFR, but lacks critical definitions.
- FLAG, underspecified: The input lacks definitions for reports, date range format, available categories, possible status values, and results format, which could materially change the effort.

---

# Gap Analysis
Readiness: Needs clarification

Q1. Which reports and report structures are available to be filtered?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: reports: The input mentions reports but does not define which reports or their structure.

Q2. What is the required date range format and what are the allowable limits?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: date range: The input mentions date range but does not define the format or allowable ranges.

Q3. Which categories exist for filtering reports?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: category: The input mentions category but does not list which categories exist.

Q4. What are the possible status values that can be filtered?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: status: The input mentions status but does not list the possible status values.

Q5. What specific results are expected, and how should they be formatted, paginated, or sorted?
   - Ask: Sarah
   - Blocking: Yes
   - Grounded in: Results: The input mentions results but does not specify the format, pagination, or sorting.

~~~
