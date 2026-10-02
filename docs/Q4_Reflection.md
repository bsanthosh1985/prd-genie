# Q4: Reflection

## What the traces showed me

**A healthy-looking pipeline can produce a wrong answer.** One Langfuse trace had all five agents present, normal token counts, and no errors. The PRD, though, had the literal placeholder title from my prompt and "Not specified" in every section. The cause was a single missing quotation mark in the Extractor's JSON, so the parse failed and every later agent received nothing. The same trace scored `story_traceability` at 1.00, because zero stories out of zero is technically a perfect ratio. I fixed it in two ways: a repair step with a safe fallback that says "SYSTEM ERROR" instead of writing a PRD, and a score that reads 0 when there is nothing to check.

**Green scores did not mean the test was passed.** On T3 (the contradictory dashboard input) both scores were 1.00, yet neither measured whether the contradiction was caught. That is why I added per-test checks that mirror the brief's "must contain" and "must NOT" conditions.

**Small changes broke things in unexpected places.** My first full run passed 9 of 12. The failures were specific: a vague wish was turned into a requirement (T2), acceptance criteria were filed as requirements (T4), and a stakeholder conflict was not recorded (T6). Later, changing the model on one agent made T2 fail one check. Each failure pointed to one line of one prompt, and the regression suite found the model-change problem before I had noticed anything.

**Output varies between runs.** The same input sometimes produced a different missing-information list, and the JSON needed repair in two of ten runs on one occasion and in none on others. A single passing run is weak evidence.

## What I would improve
1. Add the human approval step between extraction and PRD generation. It is designed but not built.
2. Add an LLM-as-judge faithfulness check on the PRD and stories, since my grounding score only covers the Extractor.
3. Build a held-out test set from anonymized real transcripts. I tuned prompts on the same 12 tests I report, so 12/12 shows the baseline is met, not that the system generalizes.
4. Apply JSON repair, or native structured output, to every agent, and record latency in the traces.
5. Split multi-meeting files before processing, and move tracing to Langfuse's OpenTelemetry endpoint before the 16 November 2026 shutdown of the endpoint I use.

## Risks of AI-generated PRDs
- **Invented or altered requirements.** A fabricated line in a PRD becomes engineering work. Verbatim source quotes and a grounding score reduce this but do not remove it.
- **False completeness.** A tidy ten-section document looks finished even when the input was thin. This is why empty sections say "Not specified" and why vague input produces questions instead of a PRD.
- **Over-reliance.** If reviewers skim, the review step becomes a rubber stamp. Mandatory review needs audits to stay honest.
- **Quietly settling disagreements.** An agent that resolves a conflict or favors one stakeholder hides a decision that belongs to people. Mine records both sides and flags them.
- **Confidentiality.** Transcripts contain sensitive discussion, and free model tiers may use prompts for training.
- **Accountability.** The PM remains the owner of the PRD, whatever drafted it.

## Connection to evaluation skills
This project taught me to turn a requirement into a test. "Must NOT add requirements" became a check that every quote appears in the input. I also learned where automated checks stop. My keyword and structure tests cannot judge neutrality or whether a priority is sensible, so those tests carry manual-review notes. The other lessons were to look for vacuous metrics, to treat prompts and model choices as versioned changes that must pass a regression suite, to separate deterministic checks from model judgment, and to avoid reporting a score from the data I tuned on. Product management has always been about writing acceptance criteria. Evaluating an AI feature is the same discipline, applied to a system that gives a different answer each time.
