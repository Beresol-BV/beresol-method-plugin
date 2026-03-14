# Beresol Method Plugin

A Claude Code plugin that implements the **Beresol Method** — a structured 5-phase, 13-step vibe-coding methodology for building projects from specification through implementation.

## What It Does

The plugin guides you interactively through each step of the method, tracks your progress, and validates project completeness before you start coding.

### Components

| Component | Type | Description |
|-----------|------|-------------|
| `beresol-method` | Skill | Core methodology knowledge — auto-activates when discussing new project setup |
| `/beresol-method` | Command | Interactive walkthrough — shows all steps, lets you pick what to do next |
| `method-validator` | Agent | Scans your project for completed steps and reports what's done vs missing |

## Installation

### Local Testing

```bash
claude --plugin-dir ~/Documents/GitHub/beresol-method-plugin
```

### Permanent Installation

Add the plugin path to your Claude Code configuration.

## Usage

### Start the Method

```
/beresol-method
```

Shows all 13 steps with progress tracking. Pick any step to work on — the order is flexible.

### Jump to a Step

```
/beresol-method 4
```

Goes directly to Step 4 (Environment File).

### Check Progress

```
/beresol-method status
```

Shows which steps are complete, partial, or missing.

### Validate Readiness

Ask Claude:
> "Are we ready to start building?"
> "What steps am I still missing?"
> "Validate my project setup"

The method-validator agent will scan your project and produce a report.

## The 13 Steps

### Phase 1: Specification & Research
1. **Master Prompt** — Exhaustive project specification (MD file)
2. **Competitive Research** — Analyse similar projects
3. **Business Model** — Document the business model (MD + HTML)

### Phase 2: Environment & Infrastructure
4. **Environment File** — Collect all API keys into `.env`
5. **Backend Services** — Configure GCP / Firebase
6. **Deployment Plan** — Define build and hosting pipeline

### Phase 3: Design & Prototyping
7. **UX/UI & Branding** — Template, logo, colour palette
8. **HTML Mockup** — Standalone visual prototype

### Phase 4: Cross-Cutting Concerns
9. **Feedback & Admin** — Feedback system + admin panel
10. **Media Fallbacks** — Stock media API integration
11. **SEO Ex Ante** — robots.txt, llms.txt, privacy, cookies, structured data

### Phase 5: Initialisation & Implementation
12. **Project Scaffolding** — .gitignore, README.md, CLAUDE.md
13. **Launch Implementation** — Begin coding

## Progress Tracking

Progress is stored in `.claude/beresol-method.local.md` within each project. This file is local and should not be committed to git.

## Author

Victor Sole Ferioli — [Beresol](https://beresol.eu)

## Licence

MIT
