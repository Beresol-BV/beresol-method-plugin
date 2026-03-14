---
name: beresol-method
description: The Beresol Method — a structured 5-phase, 13-step vibe-coding methodology for building projects. Use when the user mentions starting a new project, scaffolding an app, setting up a codebase, planning a build, or asks about the Beresol Method. Also triggers on phrases like "new project", "start from scratch", "project setup", "let's build", "scaffold", "kickoff", or "how should I structure this project".
---

# The Beresol Method

A structured approach to vibe-coding developed by Victor Solé Ferioli (Beresol). Front-loads all decision-making into specification and design so that implementation with AI coding assistants is fast and accurate.

## Core Philosophy

The method's power lies in **upfront investment**: days spent on specification, environment setup, design, and cross-cutting concerns pay off in dramatically faster, more accurate implementation. Every decision is made before a single line of application code is written.

## The 5 Phases and 13 Steps

### Phase 1: Specification & Research

**Step 1 — Master Prompt (MD file)**
Write an exhaustive specification covering: project purpose, architecture (monolith vs separated backend/frontend), tech stack, file naming convention (kebab-case / snake_case / PascalCase), static vs dynamic pages, languages and locales (British English primary; plus ES, IT, FR, NL, CA as needed), component structure, routing, and design constraints. This step often takes days — that is expected and necessary.

**Step 2 — Competitive Research**
Research similar projects and identify features, UX patterns, or technical approaches worth emulating. Incorporate findings into the master prompt.

**Step 3 — Business Model Document**
Document the business model (even for non-profit projects) in an MD file, accompanied by an HTML file for visual presentation.

### Phase 2: Environment & Infrastructure

**Step 4 — Environment File**
Collect all API keys and credentials before writing code: Google Console, Firebase, AI provider (OpenAI / Anthropic / Mistral / Qwen / DeepSeek), Pexels (stock media), email service, and any other integrations. Store in `.env`.

**Step 5 — Backend Services**
Set up Google Cloud and Firebase with their respective env variables for authentication, database, storage, and cloud functions.

**Step 6 — Frontend Deployment Plan**
Define the deployment pipeline. Default: SiteGround hosting via `npm run build` producing a `dist/` folder.

### Phase 3: Design & Prototyping

**Step 7 — UX/UI Template & Branding**
Choose a base template from webtemplates.beresol.eu (or another source). Upload the project logo to `public/assets/` and extract its HEX colour palette to define design tokens.

**Step 8 — HTML Mockup**
Create a standalone HTML file visualising the full project as described in the master prompt. Use it to assess layout, flow, and content — and iterate before committing to real implementation.

### Phase 4: Cross-Cutting Concerns

**Step 9 — Feedback & Admin Systems**
Plan a feedback mechanism linked to the project's contact email and an admin panel with restricted access.

**Step 10 — Media Fallbacks**
Integrate a stock media API (e.g. Pexels) so the project can pull open-source images automatically when needed.

**Step 11 — SEO Ex Ante**
Before deployment, prepare: `robots.txt`, `llms.txt`, cookie consent, privacy policy, SPA routing configuration, structured data / Schema.org markup, and Open Graph meta tags.

### Phase 5: Initialisation & Implementation

**Step 12 — Project Scaffolding**
Create `.gitignore`, `README.md`, and `CLAUDE.md` with all conventions, commands, and architecture decisions documented.

**Step 13 — Launch Implementation**
With the spec complete, env configured, mockup approved, and scaffolding in place — begin coding. Precise terminology in prompts leads to faster, more accurate implementation.

## Flexibility

The 13 steps are not rigid. Users may reorder them based on their project's needs. Some steps may be skipped if not applicable (e.g. not every project needs Pexels or Firebase). The method is a guide, not a cage.

## Progress Tracking

Use a `.claude/beresol-method.local.md` file in the project directory to track which steps have been completed, with notes on decisions made at each step.

For detailed guidance on each step, see the reference files in `references/`.
