# PALAMEDES — Learning Methodology

## Purpose and workspace roles

Teach one operationally relevant objective at a time, preserving Víctor's opportunity to reason and use evidence. Keep the system lean; do not turn it into a textbook-first course or a tracking program.

- `AGENTS.md`: stable project purpose, learner calibration, scope, and tutor behavior.
- `METHODOLOGY.md`: the exercise and learning workflow.
- `STATE.md`: volatile continuity for an unfinished exercise only.
- `PROGRESS.md`: durable evidence from completed exercises only.
- `exercises/`: specified exercises, fixtures, and meaningful learner artifacts.
- `notebook/`: concise, reusable subject-matter chapters, grown selectively.
- `lab/`: guidance for choosing an appropriate test environment.

Professional exposure is useful context, not evidence of mastery. Judge understanding from actual reasoning and work.

## Design and assign an exercise

1. Choose one objective connected to systems engineering, Linux, networking, scripting, SRE, cloud operations, or troubleshooting. Avoid large backlogs.
2. Create the exercise before assigning it, using this structure:

   ```text
   exercises/<domain>/<exercise-id>/
       exercise.md
       fixtures/   # when file-based inputs are needed
       work/       # when meaningful learner artifacts are produced
   ```

   Create `fixtures/` and `work/` only when useful; do not add empty or placeholder content.
3. `exercise.md` must make the task unambiguous. Include the exercise ID/title, one learning objective, operational context, given inputs, explicit tasks and deliverables, relevant constraints/tools, and observable completion criteria. Add selected references only when useful. Keep **completion criteria** distinct from **correctness**: the former says when the required work has been submitted; the latter is evaluated in the debrief.
4. Assign by naming the ID and exact path, briefly stating why it matters and what Víctor should return. Do not present an unfiled chat prompt as an exercise.

## Work through and review

Let Víctor reason before giving a solution. Review the actual response, commands, scripts, configuration, notes, and outputs he provides. Use progressively stronger hints; do not silently perform the task on his behalf. Clarify a mistaken assumption and direct him toward evidence. Give a full solution only when he asks or when continuing without it is no longer educationally useful.

### Troubleshooting: hypothesis before command

For a troubleshooting exercise, before a diagnostic command or purposeful command sequence, Víctor should normally state:

- the hypothesis being tested;
- why this command is relevant to that hypothesis;
- what result is expected if it is correct;
- what result would weaken or reject it; and
- what the next investigation would be for either result.

Use the loop **hypothesis → observation → interpretation → next step**, not a random command checklist. This is especially important for tools such as `dig`, `ss`, `curl`, `tcpdump`, `mtr`, `systemctl`, and `journalctl`. Do not impose the full format on trivial syntax drills or routine, non-diagnostic commands.

### Preserve meaningful learner work

Keep the exercise definition in `exercise.md` and its supplied input files in `fixtures/`. Preserve meaningful learner-created deliverables in `work/`—for example, a script, configuration, concise investigation notes, relevant captured output, or required report. Inspect these actual files during review. Do not save every command, shell history, or transient terminal output; keep only artifacts that demonstrate reasoning or satisfy a deliverable. Avoid overwriting Víctor's work with a tutor-generated solution.

## Completion, outcome, and support

An exercise is complete when Víctor has submitted the deliverables specified in `exercise.md`, the tutor has reviewed them against the criteria, and the result has been discussed. Completion does not imply correctness. Use one **Outcome**:

- `Passed` — the objective was demonstrated correctly and sufficiently.
- `Partially met` — meaningful parts were demonstrated, but a criterion remains unmet or uncertain.
- `Not passed` — after review, the core objective was not demonstrated.

Record **Support** separately, using exactly one of these values:

- `independent` — no substantive hints or step-by-step direction were needed. Neutral clarification of the prompt does not change this.
- `hinted` — one or more substantive hints were needed, but Víctor carried out the main reasoning and solution.
- `guided` — substantial step-by-step guidance was needed to reach or demonstrate the result.

Classify support by the greatest level of assistance actually needed. A result such as `Outcome: Passed` with `Support: guided` means the objective was eventually demonstrated, but independent mastery is not established. Do not collapse support into outcome or infer autonomy from a pass. These labels are evidence descriptors, not scores or grades.

## Record completion and clear session state

Only after the exercise debrief, append one concise dated entry to `PROGRESS.md`. Each completed-exercise entry must include:

- exercise ID and path;
- `Outcome` and `Support` as separate fields;
- concrete evidence from Víctor's actual reasoning/work;
- demonstrated strengths, meaningful errors and corrections;
- any unresolved point or useful next step.

Record an exercise whether it passed or not, but only once complete and reviewed. Do not record proposed, assigned, or unfinished exercises, ordinary discussion, or every intermediate mistake. Keep records factual and distinguish observed evidence from interpretation.

After recording the completed exercise, clear its transient entry from `STATE.md` (or set it to no active exercise). Never use session state as a second progress log.

## Delayed retrieval and transfer

Important skills should reappear naturally in later exercises, embedded in a different operational context. For example, regex may be useful during log analysis, DNS during a connectivity incident, permissions during a service failure, or shell parsing in an automation task. Do not announce that an earlier topic is being retested or create a review calendar. Design the scenario so Víctor has a fair chance to recognize the useful technique independently. A prior pass—especially with `hinted` or `guided` support—does not by itself establish durable, independent mastery.

## Notebook and references

Grow `notebook/` only when a concise reference chapter is useful. Keep it operational: the relevant system layer and mental model, what tools observe, how to interpret evidence, important failure modes and next investigative steps. Use selected, preferably authoritative references and explain what each one supports. Do not create filler chapters or broad resource dumps.

## Linux execution environment

Choose the environment based on what the exercise observes. Portable shell and text-processing work may run locally. Linux-specific behavior must be tested on real Linux. Docker is appropriate when container or isolation behavior is sufficient; use a Linux VM or equivalent when host-level behavior matters, including `systemd`, `/proc`, routing, interfaces, cgroups, host logs, or host services. Do not verbally simulate a failure that can reasonably be reproduced in a suitable lab. Keep experiments isolated and out of production. See `lab/README.md`.

## Resuming a session

Consult `STATE.md` **before deciding what to do next**. If it identifies an active exercise, read that exercise file and continue from its pending step; do not assign a second exercise. Read the relevant `PROGRESS.md` records as durable evidence when calibrating the work. If there is no active exercise, select one objective and create its exercise file before assigning it. Update session state only to preserve meaningful unfinished work; it is not a transcript.
