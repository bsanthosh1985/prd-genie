# PRD Genie: 5-Minute Demo Video Script

**Format:** screen recording with voice-over. The deck (`PRD_Genie_Capstone_Deck.pptx`) is the spine, with live screens for the demo, canvas, traces, and results.
**Length:** 5:00 maximum. The narration below is about 600 words, which at a calm pace leaves room for pauses and on-screen action.

## Before you record

**Prepare the demo data (about 15 minutes)**
- [ ] Empty the Drive **Outputs** folder, then run the Drive Intake workflow once with your three files. Let it finish, so the Outputs folder holds three `PRD_*.md` files you can show.
- [ ] Pick the best of the three outputs and make sure it shows a PRD, epics and stories, and a gap analysis.
- [ ] Keep one clean Langfuse trace open (a full-pipeline run with both scores visible).
- [ ] Have the final results file (`prdgenie_test_results_FINAL`, Markdown or the table) ready to open.

**Set up the screen**
- [ ] Resolution 1920x1080, browser zoom 125% so text is readable, notifications off, bookmarks bar hidden.
- [ ] Open these tabs in this order: (1) deck in Present mode, (2) Drive Inbox folder, (3) n8n Drive Intake workflow, (4) Drive Outputs folder, (5) one generated PRD file, (6) n8n Main workflow canvas, (7) Langfuse trace, (8) test results.
- [ ] **Never show** credential screens, API keys, the Langfuse key page, or the Pinecone key page.

**Rehearse once with a timer.** If you run long, shorten slides 5 and 8 first.

## Timeline

| Time | On screen | Length |
|---|---|---|
| 0:00 | Slide 1: cover | 0:10 |
| 0:10 | Slide 2: problem | 0:25 |
| 0:35 | Slide 3: idea | 0:25 |
| 1:00 | Slide 4: architecture, then n8n Main canvas | 0:45 |
| 1:45 | Slide 5: trust | 0:35 |
| 2:20 | **Live demo:** Drive Inbox, run workflow, Outputs, open a PRD | 1:00 |
| 3:20 | Slide 7: evidence, then results file | 0:25 |
| 3:45 | Slide 8: lessons, then a Langfuse trace | 0:35 |
| 4:20 | Slide 9: cost | 0:15 |
| 4:35 | Slide 10: limits and next steps, repo link | 0:25 |

## Shot by shot

### 1. Cover (0:00 to 0:10)
**Show:** slide 1.
**Say:**
> Hi, I'm Santhosh. This is PRD Genie. It turns meeting notes into PRDs, epics, and user stories, and it won't invent what the notes don't say.

### 2. The problem (0:10 to 0:35)
**Show:** slide 2.
**Say:**
> Product managers lose a lot of time turning meetings into requirements. Scope is buried in transcripts, PRDs are written by hand, every PM uses a different format, and notes end up in documents nobody reopens. The result is delay, inconsistent tracking, and slower time to market.

### 3. The idea (0:35 to 1:00)
**Show:** slide 3.
**Say:**
> PRD Genie takes a transcript, brief, or notes, from a form or a Google Drive folder, and produces four things: a structured PRD, epics and user stories, clarification questions, and size estimates. When the input is thin, it asks questions instead of guessing.

### 4. Architecture (1:00 to 1:45)
**Show:** slide 4 for the first 30 seconds, then switch to the n8n Main workflow canvas and zoom out so the whole pipeline is visible for about 10 seconds.
**Say:**
> It's a sequential pipeline built in n8n, because every input needs the same stages in the same order. An input guard stops empty notes. The extractor separates what was stated from what's ambiguous, and quotes the source for every requirement. If there isn't enough to write a PRD, a gap analyzer returns questions instead. Otherwise Pinecone supplies the PRD template, the generator writes ten sections, and story breakdown creates epics and stories. Gap analysis and size estimates then run in parallel, and Langfuse traces every agent.

**Click:** hover over the Extractor, the Pinecone retrieval node, and the two parallel agents on the canvas as you name them.

### 5. Trust (1:45 to 2:20)
**Show:** slide 5.
**Say:**
> The design rule is that every requirement traces back to the input. Each one carries a verbatim quote, and a score checks that the quote is really there. Empty sections say "not specified" instead of inventing goals. Conflicts between stakeholders are recorded for people to resolve, never settled by the model. And Pinecone controls format only: tests check that its content never leaks into a PRD.

### 6. Live demo (2:20 to 3:20)
**Show and click, in order:**
1. **Drive Inbox folder** with the three meeting files visible. *Say:* "Here is the Inbox with three meeting files."
2. **n8n Drive Intake workflow.** Click **Execute workflow** on the manual trigger. *Say:* "I run the Drive Intake workflow. It loops through the files and runs each one through the full pipeline. That takes a few minutes, so I've cut ahead."
3. **Cut.** Keep about 10 seconds of the workflow running, then jump (see the recording tips) to the next shot.
4. **Drive Outputs folder** showing three `PRD_*.md` files. *Say:* "In the Outputs folder there is one PRD file per input."
5. **Open one file** and scroll slowly. *Say:* "The PRD has ten sections. Where the notes didn't say, it says 'not specified'."
6. Scroll to the **epics and stories.** *Say:* "Then the epics and stories, each with a priority, its source requirement, and a size."
7. Scroll to the **gap analysis.** *Say:* "And at the end, questions for stakeholders, each grounded in a specific gap."

**Tip:** slow down on step 5. Pause for two seconds on a "Not specified in source" line, since it shows the grounding rule in action.

### 7. Evidence (3:20 to 3:45)
**Show:** slide 7 for 15 seconds, then the results file (table with 12 rows, all PASS) for about 8 seconds.
**Say:**
> On the baseline from the project brief, all 12 tests pass. It started at 9 of 12, and each failure named its cause and was fixed with one prompt rule. I should be clear that I tuned on these same tests, so this shows the baseline is met, not that the system generalizes.

### 8. What the traces taught me (3:45 to 4:20)
**Show:** slide 8 for 15 seconds, then the Langfuse trace (agent generations in the tree, the two scores on the Scores tab) for about 15 seconds.
**Say:**
> Langfuse taught me three things. One missing quotation mark in the model's JSON produced a blank PRD while the trace looked normal, so now there's a repair step and a safe fallback. A score of zero stories out of zero read 1.00, so now a broken run scores zero. And swapping the model on one agent broke one test, which the regression suite caught.

### 9. Cost (4:20 to 4:35)
**Show:** slide 9.
**Say:**
> A full run costs about half a cent: roughly five model calls and five to six thousand tokens. The whole ten-input test suite costs about five cents.

### 10. Limits and close (4:35 to 5:00)
**Show:** slide 10, with the repo link visible. Replace the placeholder with your real link before recording.
**Say:**
> What's not done: the human approval step is designed but not built, the Drive path isn't in the automated suite, and I tuned the prompts on the same tests. Next I'd add approval, build a held-out set from real transcripts, and move tracing to OpenTelemetry before Langfuse's old endpoint closes on 16 November. The code, tests, and write-ups are in the GitHub repo. Thanks for watching.

## If something goes wrong

| Problem | What to do |
|---|---|
| The Drive run fails or hangs while recording | Stop the take, show the Executions list of the earlier successful run (green), then continue with the Outputs folder |
| A model call is slow | Cut the waiting; say "I've cut ahead" so the edit is honest |
| Langfuse is slow to load | Open the trace tab a few minutes before recording |
| You run past 5:00 | Shorten slides 5 and 8, and keep the live demo intact |
| An output looks odd on camera | Open a different one of the three files; do not re-run on camera |

## Recording and export tips

- **Tools:** Loom, OBS Studio, Zoom's local recording, or PowerPoint's built-in recording all work. Record the voice-over separately if your room is noisy.
- **One pass or two:** record the slide parts in Present mode, then the screen parts, and join them in an editor (even a basic one). Keep a visible cut on the Drive run and say that you cut it.
- **Voice:** speak slower than feels natural. Read the narration aloud twice before recording, then talk to the screen instead of reading.
- **Captions:** add them if your tool offers them, since reviewers may watch without sound.
- **Export:** MP4 at 1080p. If you upload to YouTube or Loom, set the link to unlisted and test it from a private window.
- **Name it:** `PRD_Genie_Demo.mp4`.

## Final checklist before submitting
- [ ] 5:00 or shorter
- [ ] No credentials, keys, or secret screens visible anywhere
- [ ] Repo link on the last slide is real
- [ ] Mentions the limits honestly (approval step, tuning on the same tests)
- [ ] Link works in a private browser window
