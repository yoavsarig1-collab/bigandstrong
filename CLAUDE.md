# bigandstrong

A training/workout-log PWA: session-first tracker with a workout generator,
history, and PRs. No build step, no framework, no dependencies beyond Google
Fonts.

- `index.html` — the live app.
- `v3.html` — a prior design iteration, kept for reference. Don't edit it
  unless asked; changes belong in `index.html` unless told otherwise.
- `data/backup.json` — a data export/backup, not app source.

State lives in a single global `state` object, persisted to `localStorage`
under key `SK` (`persist()` / `loadState()`). All JS is one inline
`<script>` block; CSS is one inline `<style>` block with CSS custom
properties for the palette. Sections are marked with `═══` banner comments
— keep using them, don't switch to a different convention mid-file.

## How to work here

Quality over speed, and over quantity. This is a small app people actually
use — every screen and every line should feel deliberate, not generated.

- **Measure twice, cut once.** Read the surrounding code before touching
  it. Understand the existing pattern (state shape, render flow, naming)
  before adding to it. Don't guess at how a function is used elsewhere —
  check.
- **Plan, then execute.** For anything beyond a one-line fix, work out the
  approach — what changes, what it touches, what could break — before
  writing code. Non-trivial changes deserve a moment of design, not a
  first draft treated as final.
- **Ask when it matters.** If a request is ambiguous, or a change has real
  tradeoffs (data migration, UX behavior, visual direction), ask rather
  than assume. Silent guesses on things the user actually cares about are
  worse than a short question.
- **Match the house style.** This codebase is dense, terse, and
  hand-tuned — short function names, minimal whitespace, no framework
  ceremony. New code should read as if the same person wrote it, not as
  a pasted-in generic pattern.
- **No slop.** No speculative abstractions, no unused options, no
  defensive code for cases that can't happen, no comments that restate
  the code. Every addition should earn its place.
- **Robustness where it counts.** This app is the source of a user's
  workout history — protect `state` and `persist()`/`loadState()` paths
  especially carefully. Don't ship a change that can silently corrupt or
  drop logged data.
- **Verify before calling it done.** For UI changes, actually check the
  screen (open it, click through the flow) rather than assuming the code
  is correct because it looks right.

Less slop, more beautiful things.
