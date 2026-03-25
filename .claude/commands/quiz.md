---
description: Generate practice exam questions
---

Activate the cissp-exam skill. Generate questions based on this request: $ARGUMENTS

Read `/reference/cissp-glossary.md` and `/reference/exam-traps.md` first to ensure question accuracy.

If the request is "20" or "give me 20", use the domain weighting from `/reference/cissp-domains.md`.
If the request is a specific topic, generate 10 questions on that topic.
If the request is "full", generate 150 questions across all domains.
If no argument given, generate 10 mixed questions weighted toward weak areas from `/progress/daily-scores.md`.

After grading, log results to `/progress/daily-scores.md`.
