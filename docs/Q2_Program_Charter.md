# Q2: Program Charter. PRD Genie

**Program owner:** AI PM/TPM, Product and Innovation team, NeuronForge Technologies
**Status:** Prototype built and tested (12/12 baseline); pilot proposed
**Note on figures:** NeuronForge is a case scenario, so the pilot size, timeline, and targets below are my proposals. Baselines have not been measured and are set in the first two weeks of the program.

## 1. Vision

Every product decision made in a meeting becomes a traceable, consistently formatted requirement within hours, and nothing the stakeholders said is lost or invented along the way. PMs and TPMs spend their time on judgment and stakeholder conversations, not on transcribing and reformatting.

## 2. Problem and objectives

**Problem (from the brief):** PMs spend a disproportionate share of their time extracting scope from meetings and translating it into PRDs, epics, and stories. Formats differ between PMs, which makes estimation hard. Transcripts and notes are never revisited, so requirements get lost. The result is delay, inconsistent tracking, and slower time to market.

| # | Objective | Why it matters |
|---|---|---|
| O1 | Cut the time from meeting end to a reviewed PRD draft | Directly addresses the time lost to manual extraction and drafting |
| O2 | Make every PRD follow one structure | Lets engineering estimate from a predictable shape |
| O3 | Keep every generated requirement traceable to the source | Trust is the adoption risk; one invented requirement can cost more than the time saved |
| O4 | Surface gaps and contradictions before engineering sees the PRD | Moves rework from development to the meeting follow-up |
| O5 | Process new notes automatically so they are not left unread | Addresses requirements lost in unvisited documents |

## 3. Scope

**In scope (Phase 1)**
- Text inputs: meeting transcripts, product briefs, and stakeholder notes, via a form or a Google Drive folder
- Five agents: Requirement Extractor, PRD Generator, Story Breakdown, Gap Analyzer, Scope Estimator
- A ten-section PRD template delivered through Pinecone retrieval
- Observability in Langfuse and a 12-test regression suite
- Mandatory human review of every generated PRD before it is shared

**Out of scope for Phase 1**
- Audio or video transcription, and scanned documents without a text layer
- Automatic push to Jira or other trackers (Phase 3)
- Approving, prioritizing, or deciding anything on a PM's behalf. Priorities and sizes are suggestions.
- Effort estimates in hours or days
- Legal or compliance review of requirements

## 4. Success criteria

| Metric | Proposed target | How it is measured |
|---|---|---|
| Time from meeting end to reviewed PRD draft | 50% lower than baseline | PM time log during the pilot against the baseline from weeks 1 and 2 |
| PRD structure conformance | 100% of generated PRDs have all ten sections | Automated check on every run |
| Grounding (`quote_grounding` in Langfuse) | 1.0 on at least 95% of runs; every lower score reviewed | Langfuse scores, weekly review |
| Unsupported requirements found in PM review | Fewer than 1 per 20 PRDs | PM review form |
| Generated stories kept without edits | At least 70% | Compare generated and final stories |
| Usefulness of clarification questions | At least 80% rated relevant | PM review form |
| Regression suite before any prompt or model change | 12/12 pass, plus a held-out set | Test runner |
| Cost per PRD | Below $0.05 (prototype observes about $0.005) | Langfuse cost data |
| PM satisfaction | At least 4 out of 5 | End-of-pilot survey |

## 5. Timeline

| Phase | When | What happens | Gate to continue |
|---|---|---|---|
| 0. Prototype | Done | Pipeline, RAG, Drive intake, tracing, and the 12-test baseline built and passing | 12/12 baseline |
| 1. Pilot preparation | Weeks 1 to 2 | Measure the manual baseline; add the human approval step between extraction and PRD generation; build a held-out test set from anonymized real transcripts; security and data-handling review; choose the production model provider | Security sign-off, held-out set passing |
| 2. Pilot | Weeks 3 to 6 | One product team of 3 to 5 PMs/TPMs; every PRD reviewed; weekly trace review and prompt fixes through the regression suite | Targets in section 4 met or understood |
| 3. Expansion | Weeks 7 to 10 | More teams; Jira export; splitting of multi-meeting files; migration of Langfuse tracing to the OpenTelemetry endpoint | Adoption and quality stable |

**Dated constraint:** Langfuse's v3 ingestion API stops accepting trace events on **16 November 2026**. The tracing migration must be finished before then, and it is the first item in Phase 1 if the program starts before that date.

## 6. Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| The model invents or alters a requirement | Medium | High | Verbatim source quotes, grounding score, mandatory PM review, regression suite |
| A complete-looking PRD hides missing information | Medium | High | Empty sections say "Not specified in source"; gap analysis asks the questions |
| Over-reliance: PMs stop reading closely | Medium | High | Required review step, sampling audits, unsupported-requirement metric |
| Confidential transcripts exposed to a model provider | Medium | High | No-training provider terms, anonymized pilot data, security review in Phase 1 |
| A model or prompt change causes a regression | High | Medium | Run the 12 tests plus held-out set on every change. The prototype's own model change broke one test, and the suite caught it. |
| A vendor API changes (Langfuse deprecation) | Certain | Medium | Dated migration milestone above |
| Free-tier rate limits or availability | Medium | Medium | Move to a paid tier for the pilot, wait between batch items |
| Poor input: multi-meeting files, scans, very long transcripts | High | Medium | Split files before processing, reject scans with a clear message, test long inputs |
| Stakeholder bias in the output | Low | Medium | Disagreements recorded neutrally and flagged for resolution, never settled by the agent |

## 7. Stakeholders

Roles are proposed, not named individuals.

| Stakeholder | Interest | Involvement |
|---|---|---|
| Executive sponsor (Head of Product and Innovation) | Time to market, consistency | Approves phase gates, receives monthly summary |
| Program owner (AI PM/TPM) | Delivery and quality of the program | Accountable for plan, prompts, and evaluation |
| PMs and TPMs (primary users) | Less manual work, trust in output | Pilot participants, review every PRD, give feedback |
| Engineering leads | PRDs they can estimate from | Review PRD format and story quality |
| Design leads | Personas and flows captured accurately | Review PRD content in the pilot |
| Security and compliance | Data handling for transcripts | Sign-off before real data enters the pipeline |
| Platform / IT | Hosting n8n, credentials, access | Environment and access setup |

## 8. Rollout plan

1. **Pilot team and onboarding.** Pick one product team. Give them a one-page guide: how to drop a file in the Inbox folder, what the output contains, and how to report a bad result. Hold a short walkthrough.
2. **Human review is mandatory in the pilot.** A PM reads and approves every PRD before it goes to engineering. Reviewers record unsupported or missing requirements.
3. **Weekly loop.** Review the lowest-scoring Langfuse traces, fix prompts, and run the regression suite before deploying any change.
4. **Gates.** Move to Phase 3 only when the section 4 targets are met or the gaps are understood and accepted by the sponsor.
5. **Expansion.** Add teams in groups, with the same onboarding. Add Jira export once the stories are trusted.
6. **Rollback.** Switch off the Drive trigger and return to the manual process. Generated files are separate from source files, so nothing is lost.
7. **Change control.** Prompt, model, and template changes are versioned, tested, and recorded.

## 9. Assumptions and dependencies

- Meetings are transcribed to text before they reach PRD Genie
- Access to n8n, Pinecone, Langfuse, Google Drive, and a Gemini API key, with a paid tier for the pilot
- PMs agree to review and give feedback
- Engineering agrees to use the template format

## 10. Open decisions

- Whether real transcripts may go to the chosen model provider, or a different provider is needed
- Who owns the PRD template and approves changes to it
- Whether stories export to Jira or to another tracker
