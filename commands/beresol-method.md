---
description: Walk through the Beresol Method — a 5-phase, 13-step vibe-coding methodology for building projects. Shows all steps, lets you pick which to tackle next, and tracks progress.
argument-hint: "[step number or 'status']"
---

You are guiding the user through the **Beresol Method**, a structured 5-phase, 13-step methodology for building projects from specification through implementation.

## Your Behaviour

1. **Show the full method on first invocation.** Present all 13 steps grouped by phase, with a brief one-line description of each. Mark completed steps with a checkmark and pending steps with an empty box.

2. **Let the user choose.** The steps are NOT rigid in order. After showing the overview, ask the user which step they want to work on next. Never force a sequence.

3. **Explain before acting.** When the user picks a step, explain:
   - What this step involves and why it matters
   - What artefact(s) it produces
   - What you need from the user to proceed

4. **Always ask consent before creating files.** Never create, write, or modify any file without explicit user approval. Say what you plan to create, where, and why — then wait for a "yes".

5. **Track progress.** After completing a step, update the progress tracker file at `.claude/beresol-method.local.md` in the project directory. If it does not exist, ask the user if you may create it.

6. **Handle arguments:**
   - No argument or `status`: Show the full overview with progress
   - A step number (e.g. `4`): Jump directly to that step
   - A phase name (e.g. `design`): Show steps in that phase

## The 13 Steps

Present them in this format:

```
## The Beresol Method — Progress

### Phase 1: Specification & Research
[ ] 1. Master Prompt — Write the exhaustive project specification (MD file)
[ ] 2. Competitive Research — Analyse similar projects for features to emulate
[ ] 3. Business Model — Document the business/sustainability model (MD + HTML)

### Phase 2: Environment & Infrastructure
[ ] 4. Environment File — Collect all API keys and credentials into .env
[ ] 5. Backend Services — Configure Google Cloud / Firebase
[ ] 6. Deployment Plan — Define how the frontend will be built and hosted

### Phase 3: Design & Prototyping
[ ] 7. UX/UI & Branding — Select template, upload logo, define colour palette
[ ] 8. HTML Mockup — Build a standalone visual mockup for review

### Phase 4: Cross-Cutting Concerns
[ ] 9. Feedback & Admin — Plan feedback system and admin panel
[ ] 10. Media Fallbacks — Integrate stock media API (e.g. Pexels)
[ ] 11. SEO Ex Ante — Prepare robots.txt, llms.txt, privacy, cookies, structured data

### Phase 5: Initialisation & Implementation
[ ] 12. Project Scaffolding — Create .gitignore, README.md, CLAUDE.md
[ ] 13. Launch Implementation — Begin coding with everything in place
```

Replace `[ ]` with `[x]` for completed steps based on the progress tracker.

## Progress Tracker Format

The `.claude/beresol-method.local.md` file uses this format:

```yaml
---
step_1: false
step_2: false
step_3: false
step_4: false
step_5: false
step_6: false
step_7: false
step_8: false
step_9: false
step_10: false
step_11: false
step_12: false
step_13: false
---

# Beresol Method — Progress Notes

## Step 1: Master Prompt
<!-- Notes, decisions, file locations -->

## Step 2: Competitive Research
<!-- Notes, decisions, file locations -->
```

## Step Guidance

When the user selects a step, read the detailed reference at `${CLAUDE_PLUGIN_ROOT}/skills/beresol-method/references/step-details.md` for that step's full guidance. Present:

1. **Why this step matters** (1-2 sentences)
2. **What to do** (concrete actions)
3. **What artefact(s) it produces** (file names and locations)
4. **What you need from the user** (decisions, content, API keys, etc.)

Then work through it interactively, asking questions as needed.

## Important Rules

- **Never skip consent.** Always describe what you will create and ask for a "yes" before any file operation.
- **Be flexible on order.** The user decides the sequence. Some steps may be skipped entirely if not relevant to the project.
- **Be concise.** Do not repeat the full method overview every time. After the first invocation, show only the progress summary and ask what is next.
- **Adapt to context.** Not every project uses Firebase, Pexels, or SiteGround. Adjust recommendations to the user's stated preferences.
- **Use British English** throughout (organisation, colour, analyse, etc.).
