# PALAMEDES — Learning Methodology

## Purpose

This document defines how we design, assign, work through, review, and record exercises. The goal is independent operational reasoning—not completing a pile of prompts or reading a large textbook before practice.

## Workspace roles

- `AGENTS.md`: stable project purpose, learner calibration, scope, and tutor behavior.
- `METHODOLOGY.md`: the exercise and learning workflow defined here.
- `notebook/`: concise, reusable subject-matter chapters with relevant references. It is not a diary of Víctor's performance.
- `exercises/`: the canonical, fully specified exercise prompts and any input fixtures. An exercise is not assigned until its file exists.
- `PROGRESS.md`: dated records of completed exercises only. It is not a running conversation log, task queue, or place for proposals and unfinished attempts.

## Exercise lifecycle

### 1. Select one learning objective

Choose one concept or operational skill at a time. Connect it to systems engineering, Linux, networking, scripting, SRE, cloud operations, or troubleshooting. Calibrate difficulty from evidence in completed exercises and the context Víctor has provided; professional experience is not itself proof of mastery.

### 2. Prepare the exercise file before assigning it

Create one clearly named Markdown file under `exercises/`, organized by topic. Include enough information that Víctor can answer “what exactly am I meant to do?” without guessing. The exercise file must state:

- **ID and title**
- **Learning objective** — the capability being tested or practised
- **Operational context** — why the problem matters and what layer is in scope
- **Given inputs** — data, logs, files, system state, or a precise verbal scenario; include fixtures where useful
- **Tasks** — explicit deliverables, in order, including what reasoning to explain
- **Constraints and allowed tools** — only where they matter
- **Completion criteria** — observable requirements for a complete response, separate from what counts as a correct result
- **References** — optional, selected sources with a note on what they clarify

Do not present an unfiled chat question as an exercise. If the prompt is vague or the expected evidence is not clear, refine the file before assigning it. Do not create a large backlog of exercises in advance.

### 3. Assign and let Víctor work

Introduce the exercise by its ID and exact file path, briefly connect it to the objective, and identify the requested deliverable. Ask for Víctor's reasoning before revealing an answer. Let him use the terminal when that gives useful evidence. Do not silently perform his task or replace his work with an AI-generated solution.

### 4. Coach without taking over

Review the actual answer, commands, scripts, and outputs Víctor provides. If reasoning is incomplete or mistaken, point to the specific assumption and ask for evidence. Offer hints progressively. Give a full solution only when Víctor asks for it or when continuing without it is no longer educationally useful. When using the terminal to verify behavior, distinguish verification of Víctor's attempt from doing the exercise for him.

### 5. Decide whether the exercise is complete

An exercise is **complete** only after Víctor has supplied the deliverables required by its file, the tutor has reviewed them against the stated criteria, and the result has been discussed. Completion is not the same as passing. After the debrief, record one outcome:

- **Passed** — the required reasoning/work is correct and sufficiently supported.
- **Partially met** — meaningful parts are correct, but a stated criterion remains unmet or uncertain.
- **Not passed** — the attempt was reviewed and the core objective was not demonstrated.

If the response is still in progress, evidence is missing, or debrief has not happened, the exercise remains open. Do not record it yet. Errors and corrections during an open exercise are captured in its final debrief record only if they are useful learning evidence.

### 6. Update the exercise record once, after completion

Only after the debrief, append a concise dated entry to `PROGRESS.md`, under that day's heading. Include:

- exercise ID, title, and file path;
- outcome (passed, partially met, or not passed);
- what Víctor actually reasoned, produced, or tested;
- what that evidence demonstrates, including strengths and any misconception/correction;
- unresolved point and next checkpoint, if there is one.

Do not update this file when an exercise is merely proposed, written, assigned, or underway. Do not add entries for ordinary discussion, setup work, learner preferences, or unverified claims. If a session has no completed exercise, `PROGRESS.md` stays unchanged. Correct a factual mistake in a previous entry only when necessary; do not use corrections as a reason to add routine status notes.

### 7. Grow the notebook selectively

Develop `notebook/` as a high-quality reference alongside the practice, not as a prerequisite course. Add or refine a chapter when the concept has enough value to preserve. Keep it focused on operational use:

1. Why the concept matters and what system layer it concerns.
2. The mental model needed to reason about it.
3. What relevant tools observe, and how to interpret the evidence.
4. A worked example or failure mode connected to real operations.
5. What to investigate next and any important caveats.
6. Relevant, preferably primary-source references, with a short note explaining their use.

Search for sources when they materially improve accuracy or depth. Prefer current official documentation and manual pages; verify that a cited page supports the claim. Avoid link dumps, broad research unrelated to the active objective, and content that does not serve practical systems engineering.

## At the start of a resumed exercise

Read `AGENTS.md`, this methodology, the relevant exercise file, and `PROGRESS.md`. Use the last completed exercise as evidence, not as a reason to repeat mastered work. If an exercise is still open in the conversation, continue that exact exercise; otherwise prepare a new exercise file before assigning anything.
