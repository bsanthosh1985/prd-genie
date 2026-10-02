# Q1: Ideation. Pain Points in NeuronForge's PM Workflow

The brief describes one bottleneck: PMs and TPMs spend their time turning meeting discussions into structured requirements, and the results are slow, inconsistent, and easy to lose. I broke that into seven concrete pain points. For each one: the manual step today, the agent that addresses it, what goes in and comes out, and the risks.

## Summary

| # | Pain point | Agent solution | Status in my build |
|---|---|---|---|
| 1 | Gathering scope from meetings takes too long | Requirement Extractor | Built |
| 2 | Writing PRDs from discussions is manual and iterative | PRD Generator | Built |
| 3 | Every PM uses a different PRD format | PRD Generator with template retrieval (Pinecone) | Built |
| 4 | Breaking PRDs into epics and stories is manual | Story Breakdown | Built |
| 5 | Gaps and contradictions surface late | Gap Analyzer, plus contradiction detection in the Extractor | Built |
| 6 | Estimation is hard because scope is unclear | Scope Estimator | Built |
| 7 | Transcripts and notes sit in documents nobody revisits | Drive Intake workflow; searchable index of past requirements | Intake built; search is future work |

## 1. Gathering scope from meetings takes too long

- **Manual step today:** Someone reads or re-watches the meeting, then pulls out features, constraints, owners, and deadlines by hand. What gets captured depends on who took the notes.
- **Agent solution:** The **Requirement Extractor** reads the transcript, brief, or notes and returns structured JSON: stated requirements, acceptance criteria, stakeholders, deadlines, dependencies, ambiguities, contradictions, and missing information. Every requirement carries a verbatim quote from the source.
- **Input to output:** Transcript, brief, or stakeholder notes, to a requirements JSON with source quotes.
- **Risks:** The model invents or rounds a requirement, or drops one. *Mitigation:* the quote must appear in the input (checked by a grounding score), numbers are copied exactly, anything inferred goes in a separate assumptions list, and a guard stops empty input before any model call.

## 2. Writing PRDs from discussions is manual and iterative

- **Manual step today:** The PM turns notes into prose across several drafts, usually filling gaps with their own assumptions along the way.
- **Agent solution:** The **PRD Generator** produces a ten-section PRD (overview, goals, personas, features, acceptance criteria, NFRs, stakeholders, dependencies and risks, assumptions, open questions) from the extraction only.
- **Input to output:** The extraction JSON, to a structured PRD in Markdown.
- **Risks:** Plausible but invented goals, personas, or assumptions make an incomplete PRD look complete. *Mitigation:* sections with no source data say "Not specified in source", assumptions are only copied from the extraction, and every open question comes from a recorded gap.

## 3. Every PM uses a different PRD format

- **Manual step today:** PMs start from personal templates or old documents, so engineering receives PRDs in different shapes and cannot estimate them consistently.
- **Agent solution:** The PRD Generator retrieves the company template and a sample past PRD from **Pinecone** and follows their structure and style. The retrieved text controls format only, never content.
- **Input to output:** Template and past PRDs (indexed once), to PRDs with identical section structure.
- **Risks:** Content from the sample leaks into a real PRD, or the template goes stale. *Mitigation:* an explicit structure-only rule, a leak check in every test (the sample is about an unrelated product so leakage is easy to see), and a versioned template.

## 4. Breaking PRDs into epics and stories is manual

- **Manual step today:** The PM or TPM rewrites each requirement as stories, assigns priorities, and copies acceptance criteria across, often differently each time.
- **Agent solution:** The **Story Breakdown Agent** produces epics, features, and "As a [user]" stories with Must / Should / Nice to Have priority, the source requirement IDs, and acceptance criteria copied word for word from the source. Separate personas get separate stories.
- **Input to output:** PRD and extraction, to a structured epic / feature / story tree.
- **Risks:** Invented acceptance criteria, merged personas, or priorities assigned without any signal in the source. *Mitigation:* criteria are copied verbatim or left empty, every story must cite a requirement, and the priority comes with a written rationale.

## 5. Gaps and contradictions surface late

- **Manual step today:** Missing details and conflicting requests are usually discovered during estimation or development, when changing course is expensive.
- **Agent solution:** The Extractor flags contradictions and ambiguities as it reads, and the **Gap Analyzer** turns them into clarification questions, each addressed to a named stakeholder, grounded in a specific gap, and marked blocking or non-blocking. Vague or incomplete input produces questions instead of a PRD.
- **Input to output:** Extraction and stories, to a prioritized list of clarification questions.
- **Risks:** Noisy questions, over-flagging everything as blocking, or the agent quietly resolving a conflict. *Mitigation:* one question per distinct gap, a rule never to resolve contradictions, and questions that must quote their source.

## 6. Estimation is hard because scope is unclear

- **Manual step today:** Engineers ask the PM what a story means before they can size it, and different PRD shapes make comparison difficult.
- **Agent solution:** The **Scope Estimator** gives each story a provisional S / M / L / XL size from signals in the source (number of capabilities, linked NFRs, dependencies, open questions) and flags underspecified stories with the open question responsible.
- **Input to output:** Stories and extraction, to a size and rationale per story.
- **Risks:** False precision, or sizes anchoring the team before they have discussed the work. *Mitigation:* sizes are labelled provisional, come with their reasoning, and are never expressed in hours or days.

## 7. Transcripts and notes sit in documents nobody revisits

- **Manual step today:** Meeting notes are saved to a shared drive and forgotten, so requirements discussed once are lost unless someone remembers them.
- **Agent solution:** The **Drive Intake** workflow processes every file dropped into an Inbox folder through the full pipeline and writes a PRD file with epics, stories, and gap analysis to a separate Outputs folder. As a next step, the extractions could be indexed in Pinecone so past requirements become searchable.
- **Input to output:** Files in a Google Drive folder, to one PRD file per input. *Future:* a searchable index of requirements across meetings.
- **Risks:** Confidential transcripts sent to a model provider, several meetings merged into one muddled PRD, and the output folder being re-read as input. *Mitigation:* use a no-training provider for real data, split multi-meeting files before processing (future work), and keep Outputs outside the watched Inbox.

## Prioritization

| Pain point | Impact | Effort | Order |
|---|---|---|---|
| 1 Scope gathering | High | Medium | 1 |
| 5 Gaps and contradictions | High | Medium | 2 |
| 2 PRD writing | High | Low | 3 |
| 4 Story breakdown | Medium | Low | 4 |
| 3 Format consistency | Medium | Low | 5 |
| 6 Estimation | Medium | Low | 6 |
| 7 Forgotten notes | Medium | Medium | 7 |

I ranked extraction first because every other agent depends on its output being faithful to the source. A PRD built on an invented requirement is worse than no PRD. The gap analysis comes second because it protects against that failure from the other side, by asking when the input is not enough.

## What this document does not claim
The time savings are not measured. The program charter defines how they would be measured in a pilot. The pain points come from the project brief and the behavior of the tests I ran, not from interviews with PMs.
