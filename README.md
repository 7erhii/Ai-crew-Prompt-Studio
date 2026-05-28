# idea-factory

Reusable specialist library + orchestrator for turning a raw idea into a
prototyping spec (docs + plan), like the AURA brand/design docs.

## How to run (through an AI agent: Cursor or terminal claude)

1. User drops a raw idea (one paragraph is enough).
2. Agent reads `DIRECTOR.md` and follows it.
3. DIRECTOR runs Phase 0 (intake) → picks specialists → runs Phase 1
   (understand) → Phase 2 (build plan).
4. Output lands in `cases/<slug>/` as numbered markdown files.

## Layout

- `DIRECTOR.md` — orchestrator. Start here. Defines phases, scale tiers,
  specialist selection, output contract.
- `specialists/NN-name.md` — one role each. Thin role + checklist + output
  contract + hard rules. Written for AI consumption, not humans.
- `cases/<slug>/` — one folder per idea (a "business case"). Generated.
- `cases/_TEMPLATE/` — empty case skeleton.

## Conventions

- All specialist files are machine-directive: imperative, terse, structured.
- A specialist NEVER writes outside its `PRODUCES` contract.
- DIRECTOR is the only file that decides sequencing and which specialists run.
- Default stack bias: Next.js (+ ecosystem) for web, React Native for mobile.
  Override only with explicit justification.
