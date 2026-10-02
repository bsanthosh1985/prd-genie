<!-- Source file: stakeholder_notes.txt | Route: COMPLETE -->

# PRD: Analytics Service and Dashboard Query Optimization
## 1. Overview
Not specified in source. See Open Questions.
## 2. Goals
Not specified in source. See Open Questions.
## 3. User Personas
- enterprise accounts
- customers
## 4. Feature List
- R4: Use the existing events table for the data model
- R6: Support multi-tenant access where customers see their own data, filtered by their account
- R7: Include search and filtering capabilities
## 5. Acceptance Criteria
Not specified in source. See Open Questions.
## 6. Non-Functional Requirements
- R1: Optimize the query layer before adding any new features
- R2: Make sure it doesn't hammer the database with expensive queries
- R3: The analytics service should be its own service, not bolted onto the monolith
- R5: Add an index on the timestamp column of the events table (full table scans take 8+ seconds)
## 7. Stakeholders and Deadlines
Stakeholders:
- Raj, Engineering Lead (Viewpoint: Focuses on API performance, moving to microservices, database query optimization, using the existing events table with an index, and backend sprint estimates.)
- Lisa, Design Lead (Viewpoint: Prefers single-page app approach, prioritizing insights over charts, desktop experience first with mobile as a fast follow, and adding dark mode.)
- Tom, VP Sales (Viewpoint: Needs something out by end of March for the board meeting, warns against losing enterprise accounts if not shipped by Q3, wants a professional look with a board-ready number, and asks for churn prediction.)
- Nina, Customer Success (Viewpoint: Emphasizes multi-tenant support for customer-specific filtered data, mentions customer requests for white-labeling, and prioritizes search and filtering over new metrics.)

Deadlines:
- end of March
- Q3
## 8. Dependencies and Risks
- Contradiction: "I'd like to explore a single-page app approach." vs "engineering prefers server-rendered pages for SEO." - Needs stakeholder resolution
- Contradiction: "Can we get something out by end of March? Even if it's basic?" vs "If we don't ship by Q3, we risk losing at least one of them." - Needs stakeholder resolution
- Contradiction: "I'd say we need at least 2 sprints for the backend work. Maybe 3 if we include the API redesign." vs "Can we get something out by end of March? Even if it's basic?" - Needs stakeholder resolution
## 9. Assumptions
- Engineering prefers server-rendered pages for SEO. (Unconfirmed)
## 10. Open Questions
- the dashboard: The dashboard is mentioned without specifying what screens, metrics, or layout it contains.
- real-time: Real-time is not defined in terms of latency or update frequency.
- budget: Budget is not mentioned or defined.
- churn prediction: Tom asks if it can predict churn without specifying what data to use or what accuracy is acceptable.
- Contradiction: Statement A: "I'd like to explore a single-page app approach." / Statement B: "engineering prefers server-rendered pages for SEO." (Needs stakeholder resolution)
- Contradiction: Statement A: "Can we get something out by end of March? Even if it's basic?" / Statement B: "If we don't ship by Q3, we risk losing at least one of them." (Needs stakeholder resolution)
- Contradiction: Statement A: "I'd say we need at least 2 sprints for the backend work. Maybe 3 if we include the API redesign." / Statement B: "Can we get something out by end of March? Even if it's basic?" (Needs stakeholder resolution)
- Which metrics or insights the dashboard must display
- What data the churn prediction should use and what accuracy is acceptable
- Whether white-labeling is in scope
- What specific search and filtering criteria are required

---

# Epics, Features and User Stories

## E1: Analytics Service and Data Model
Epic covering data model and service architecture requirements.

### F1: Data Model and Multi-Tenant Access

**US1**: As a customers, I want to use the existing events table for the data model, so that
- Priority: Must Have (Stated functional requirement with no explicit alternative priority given in the source.)
- Source requirements: R4
- Linked NFRs: R1, R2, R3, R5
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size based on leveraging the existing events table, combined with query layer optimization requirements and database constraints to prevent expensive full table scans. Scope includes distinct NFRs for query optimization, separate analytics service requirements, and database indexing.

**US2**: As a enterprise accounts, I want to support multi-tenant access where customers see their own data, filtered by their account, so that
- Priority: Must Have (Stated functional requirement with no explicit alternative priority given in the source.)
- Source requirements: R6
- Linked NFRs: R1, R2, R3, R5
- Acceptance criteria: None stated in source
- Size (provisional): L. Provisional size due to the critical multi-tenant access requirement, combined with separate analytics service architecture requirements and query optimization constraints to prevent performance degradation.

**US3**: As a customers, I want to include search and filtering capabilities, so that
- Priority: Must Have (Stated functional requirement with no explicit alternative priority given in the source.)
- Source requirements: R7
- Linked NFRs: R1, R2, R3, R5
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size covering search and filtering capabilities integrated with the query layer optimizations and analytics service architecture.
- FLAG, underspecified: What specific search and filtering criteria are required

**US4**: As a enterprise accounts, I want to include search and filtering capabilities, so that
- Priority: Must Have (Stated functional requirement with no explicit alternative priority given in the source.)
- Source requirements: R7
- Linked NFRs: R1, R2, R3, R5
- Acceptance criteria: None stated in source
- Size (provisional): M. Provisional size for search and filtering capabilities tailored to enterprise accounts, factoring in query layer optimization and multi-tenant data isolation constraints.
- FLAG, underspecified: What specific search and filtering criteria are required

---

# Gap Analysis
Readiness: Needs clarification

Q1. What specific screens, metrics, or layout does the dashboard contain?
   - Ask: Lisa
   - Blocking: Yes
   - Grounded in: the dashboard

Q2. What is the required latency or update frequency for real-time features?
   - Ask: Raj
   - Blocking: No
   - Grounded in: real-time

Q3. What is the allocated budget for this project?
   - Ask: Requester / Product Owner
   - Blocking: No
   - Grounded in: budget

Q4. What data should the churn prediction use and what accuracy is acceptable?
   - Ask: Tom
   - Blocking: No
   - Grounded in: churn prediction

Q5. Should we use a single-page app approach or server-rendered pages for SEO?
   - Ask: Lisa
   - Blocking: Yes
   - Grounded in: I'd like to explore a single-page app approach.

Q6. Is the target launch deadline end of March or Q3?
   - Ask: Tom
   - Blocking: Yes
   - Grounded in: Can we get something out by end of March? Even if it's basic?

Q7. How do we reconcile the backend estimate of 2-3 sprints with the end of March deadline?
   - Ask: Raj
   - Blocking: Yes
   - Grounded in: I'd say we need at least 2 sprints for the backend work. Maybe 3 if we include the API redesign.

Q8. Which metrics or insights must the dashboard display?
   - Ask: Lisa
   - Blocking: Yes
   - Grounded in: Which metrics or insights the dashboard must display

Q9. Is white-labeling in scope for the release?
   - Ask: Nina
   - Blocking: No
   - Grounded in: Whether white-labeling is in scope

Q10. What specific search and filtering criteria are required?
   - Ask: Nina
   - Blocking: Yes
   - Grounded in: What specific search and filtering criteria are required
