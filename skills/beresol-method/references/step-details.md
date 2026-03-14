# Step-by-Step Reference

Detailed guidance for each step of the Beresol Method.

---

## Step 1 — Master Prompt (MD file)

**Why:** This is the single most important step. A well-written spec eliminates ambiguity, reduces back-and-forth during implementation, and ensures the AI assistant understands exactly what to build. Skipping or rushing this step is the most common cause of wasted time.

**What to include:**
- Project name and one-paragraph purpose
- Target audience and use cases
- Tech stack: framework (React, Vue, Next.js, etc.), language (TypeScript, Python), styling (Tailwind, CSS Modules), package manager (pnpm, npm, yarn)
- Architecture: monolith, separated frontend/backend, serverless, JAMstack
- File naming convention: kebab-case, snake_case, PascalCase — pick one and be consistent
- Page structure: list every route/page with its purpose
- Component hierarchy: how components relate and nest
- Data model: what data the app stores and how
- Internationalisation: primary language (British English), additional locales
- Third-party integrations: APIs, services, databases
- Design constraints: responsive breakpoints, accessibility, performance targets

**Artefact:** A markdown file at the project root (e.g. `docs/instructions.md`, `docs/spec.md`, or `BRIEF.md`).

---

## Step 2 — Competitive Research

**Why:** No project exists in a vacuum. Understanding what competitors do well (and poorly) saves time and produces a better result. You do not need to reinvent solutions that already exist.

**How to do it:**
- Ask Claude Code to research 3-5 similar projects or products
- Identify features, UX patterns, visual design choices, or technical approaches worth emulating
- Note what competitors do poorly — avoid those mistakes
- Incorporate findings into the master prompt

**Artefact:** Notes in the master prompt or a separate file (e.g. `docs/competitive-research.md`).

---

## Step 3 — Business Model Document

**Why:** Even non-profit projects need a sustainability model. Documenting the business model forces clarity about who the project serves, how it generates value, and what resources it requires.

**What to include:**
- Value proposition
- Target customers/users
- Revenue streams (or funding model for non-profits)
- Cost structure
- Key partnerships and resources

**Artefact:** An MD file (e.g. `docs/business-model.md`) plus an HTML file for visual presentation (e.g. `docs/business-model.html`).

---

## Step 4 — Environment File

**Why:** Collecting all API keys upfront prevents interruptions during implementation. Nothing kills flow like having to stop coding to register for an API, wait for approval, or debug authentication.

**Common keys to collect:**
- `GOOGLE_CLIENT_ID`, `GOOGLE_CLIENT_SECRET` — Google Console
- `FIREBASE_API_KEY`, `FIREBASE_AUTH_DOMAIN`, `FIREBASE_PROJECT_ID` — Firebase
- `OPENAI_API_KEY` or `ANTHROPIC_API_KEY` or `MISTRAL_API_KEY` — AI provider
- `PEXELS_API_KEY` — Stock media
- `EMAIL_SERVICE_API_KEY` — Email (SendGrid, Resend, etc.)
- `VITE_*` prefix for any keys needed in the frontend (Vite projects)

**Artefact:** A `.env` file at the project root (never committed to git).

---

## Step 5 — Backend Services

**Why:** Backend infrastructure (auth, database, storage) needs to be configured before the application can use it. Setting it up early ensures the frontend can connect to real services from the start.

**Default stack:** Google Cloud Platform + Firebase
- Firebase Auth for authentication
- Firestore or Realtime Database for data
- Firebase Storage for file uploads
- Cloud Functions for serverless logic

**Artefact:** Firebase project created, env variables in `.env`, Firebase config in the codebase.

---

## Step 6 — Frontend Deployment Plan

**Why:** Knowing how the project will be deployed influences build configuration, asset handling, and routing setup. Decide this early to avoid rework.

**Default approach:** SiteGround hosting
- `npm run build` → `dist/` folder
- Upload `dist/` contents to SiteGround via File Manager or SFTP
- Configure `.htaccess` for SPA routing if needed

**Alternatives:** Vercel, Netlify, Cloudflare Pages, GitHub Pages — each has its own configuration.

**Artefact:** Deployment notes in `CLAUDE.md` or `README.md`.

---

## Step 7 — UX/UI Template & Branding

**Why:** Starting from a template saves days of design work and ensures visual consistency. Extracting colours from the logo creates a cohesive brand identity without a designer.

**How to do it:**
1. Browse webtemplates.beresol.eu (or another template source)
2. Pick a template that matches the project's tone and layout needs
3. Upload the project logo to `public/assets/` (or `public/images/`)
4. Extract the logo's HEX colour palette (3-5 colours)
5. Define these as design tokens in Tailwind config or CSS variables

**Artefact:** Logo file in `public/assets/`, colour palette in `tailwind.config.ts` or `:root` CSS variables.

---

## Step 8 — HTML Mockup

**Why:** A standalone HTML mockup lets you see the full project visually before writing any React/Vue/framework code. It is far cheaper to iterate on a static HTML file than to refactor a component tree.

**What to include:**
- All major pages/sections represented
- Real (or realistic) content, not lorem ipsum where possible
- The colour palette and branding from Step 7
- Responsive layout (test at mobile, tablet, desktop)
- Navigation flow between sections

**Artefact:** A standalone HTML file (e.g. `docs/mockup.html`).

---

## Step 9 — Feedback & Admin Systems

**Why:** Every project needs a way for users to give feedback and for the owner to manage content. Planning these upfront ensures they are integrated cleanly rather than bolted on later.

**Default pattern:**
- Feedback: A form or CTA that sends emails to the project's contact address
- Admin panel: A protected route/page accessible only to the project owner's email address
- Authentication: Use Firebase Auth with email allowlisting

**Artefact:** Design notes in the master prompt or spec.

---

## Step 10 — Media Fallbacks

**Why:** Projects often need images (hero backgrounds, placeholders, content illustrations). Having an API-based fallback means the project always has access to quality imagery without manual sourcing.

**Default approach:** Pexels API
- Free, high-quality stock photos
- API key required (add to `.env`)
- Search by keyword, curated collections
- Respect Pexels attribution requirements

**Alternatives:** Unsplash API, Pixabay API, or pre-downloaded assets.

**Artefact:** API key in `.env`, utility function for fetching images.

---

## Step 11 — SEO Ex Ante

**Why:** SEO is much harder to retrofit than to build in from the start. Preparing these files before deployment means search engines can index the site correctly from day one.

**Files to create:**
- `robots.txt` — Tell crawlers what to index
- `llms.txt` — Describe the site for AI crawlers
- Cookie consent banner/component
- Privacy policy page
- SPA routing config (for proper crawling of client-side routes)
- Structured data (Schema.org JSON-LD)
- Open Graph and Twitter Card meta tags (in a reusable SEO component)

**Artefact:** Files in `public/` and components for meta tags.

---

## Step 12 — Project Scaffolding

**Why:** These foundational files set expectations for contributors (human and AI) and prevent common mistakes.

**Files to create:**
- `.gitignore` — Exclude node_modules, .env, dist, OS files, IDE files
- `README.md` — Project overview, setup instructions, available commands
- `CLAUDE.md` — All conventions, commands, architecture, project structure for Claude Code

**Artefact:** Three files at the project root.

---

## Step 13 — Launch Implementation

**Why:** By this point, every decision has been made. The AI assistant has a complete spec, configured environment, visual mockup, and documented conventions. Implementation should be fast and accurate.

**Key principle:** Use precise software development and AI/ML terminology in your prompts. Vague language leads to vague results. The jargon exists for a reason — use it.

**Artefact:** The project itself.
