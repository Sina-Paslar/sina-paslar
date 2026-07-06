# "Currently Building" Section Expansion — Design

Date: 2026-07-06

## Goal

Expand the README's "Currently Building" section from one-line bullets back
into full per-project write-ups ("that is what represents me"), and add
motion via animated tech-stack icons per project. Builds on top of the
visually-polished README from
`2026-07-06-github-profile-readme-visual-polish-design.md`.

## Decisions (agreed with user)

- **Detail level:** full sections per project — heading + subtitle,
  description paragraph, 3 bullet points, tech-icon row, "Key areas" line.
  This restores the original (pre-trim) project write-ups verbatim in prose,
  with the plain-text "Languages & Technologies" line replaced by an
  animated icon row.
- **Motion:** animated tech-stack icon badges via the `readmecodegen.com`
  Social Icon Generator API (`/api/social-icon?name=X&animation=pulse&size=40`),
  one icon row per project (not per main Tech Stack grid — that section is
  explicitly out of scope for this change).
- **GLIP stays text-only** — no icon row, matching its original non-technical
  nature (no "Languages & Technologies" line existed for it before either).

## Reliability verification (done during brainstorming, not assumed)

Live-tested `https://www.readmecodegen.com/api/social-icon` before adopting
it, since a similar-sounding free image service (`github-readme-stats`)
broke earlier today:

- Returns `200 OK`, `Content-Type: image/svg+xml`, with `Cache-Control:
  public, max-age=31536000, immutable` (aggressively cached — good for
  reliability).
- The SVG body contains a self-contained `<style>` block with CSS
  `@keyframes` (e.g. `pulse`) — the animation is baked into the SVG file
  itself, not injected page CSS, so it survives GitHub's markdown
  sanitizer the same way `readme-typing-svg` does.
- Confirmed working slugs (HTTP 200): `python`, `typescript`, `javascript`,
  `java`, `go`, `php`, `react`, `nextjs`, `tailwindcss`, `supabase`,
  `postgresql`, `neo4j`, `mongodb`, `git`, `docker`, `vitest`, `posthog`,
  `pydantic`, `json`, `testinglibrary`, `googlegemini`.
- Confirmed **not** working (HTTP 404, all variants tried): `vscode` /
  `vs-code` / `visualstudiocode` / `visual-studio-code` (user decided:
  drop VS Code from any icon row rather than use a workaround), `cobol`
  (expected — no COBOL icon exists anywhere, stays a shields.io text
  badge elsewhere in the README, unaffected by this change), `cypher`
  (Neo4j's query language — mentioned in the Course Similarity Graph
  project's bullet text only, no icon).

## File

- Modify: `README.md` — only the "Currently Building" section changes.
  No other section (header, About Me, Tech Stack, Contribution Activity,
  closing quote) is touched.

## Final "Currently Building" section content

```markdown
## Currently Building

### Auspicious App — Accessibility & Learning Platform

A client-facing web application focused on improving accessibility, usability, and learning support for entrepreneurs and learners.

- Managed team coordination, client communication, project scope, and feature planning.
- Worked on accessibility features including contrast settings, font/text customization, motion controls, and personalized user preferences.
- Used modern full-stack technologies including Next.js, TypeScript, Tailwind CSS, Supabase, and PostHog.

<p>
  <img src="https://www.readmecodegen.com/api/social-icon?name=typescript&animation=pulse&size=40" alt="TypeScript" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=javascript&animation=pulse&size=40" alt="JavaScript" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=react&animation=pulse&size=40" alt="React" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=nextjs&animation=pulse&size=40" alt="Next.js" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=tailwindcss&animation=pulse&size=40" alt="Tailwind CSS" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=supabase&animation=pulse&size=40" alt="Supabase" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=posthog&animation=pulse&size=40" alt="PostHog" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=vitest&animation=pulse&size=40" alt="Vitest" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=testinglibrary&animation=pulse&size=40" alt="React Testing Library" />
</p>

**Key areas:** Full-stack development, accessibility, project leadership, client collaboration, testing.

---

### Hippodamus — Construction Safety & Project Workflow Platform

A software project focused on construction safety workflows, stakeholder coordination, and practical safety-management processes.

- Managed team direction and helped organize development tasks across the project.
- Contributed to product planning, workflow analysis, and feature breakdowns for safety-related use cases.
- Focused on turning real stakeholder problems into clear software requirements and user stories.

<p>
  <img src="https://www.readmecodegen.com/api/social-icon?name=typescript&animation=pulse&size=40" alt="TypeScript" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=javascript&animation=pulse&size=40" alt="JavaScript" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=react&animation=pulse&size=40" alt="React" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=nextjs&animation=pulse&size=40" alt="Next.js" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=tailwindcss&animation=pulse&size=40" alt="Tailwind CSS" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=supabase&animation=pulse&size=40" alt="Supabase" />
</p>

**Key areas:** Product design, workflow analysis, team leadership, safety-tech, stakeholder communication.

---

### Course Similarity Graph — AI + Graph Database System

A graph-based system for comparing college and university courses across institutions using extracted course topics and relationships.

- Supervised developers and helped coordinate the ingestion and extraction workflow.
- Built a course-similarity model using Neo4j, graph relationships, Python, and LLM-based topic extraction.
- Designed graph queries to compare courses by shared topics, institutions, programs, and relationships.

<p>
  <img src="https://www.readmecodegen.com/api/social-icon?name=python&animation=pulse&size=40" alt="Python" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=neo4j&animation=pulse&size=40" alt="Neo4j" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=googlegemini&animation=pulse&size=40" alt="Gemini API" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=pydantic&animation=pulse&size=40" alt="Pydantic" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=docker&animation=pulse&size=40" alt="Docker" />
  <img src="https://www.readmecodegen.com/api/social-icon?name=json&animation=pulse&size=40" alt="JSON" />
</p>

**Key areas:** Python, Neo4j, GraphRAG, LLM extraction, database modeling, team supervision.

---

### GLIP — Startup / Product Development Project

A product-focused project involving entrepreneurship, market research, business planning, and early-stage software development.

- Worked on defining the problem, target users, value proposition, and product direction.
- Applied startup-development skills including market research, stakeholder communication, and go-to-market thinking.
- Connected technical development decisions with real user and business needs.

**Key areas:** Entrepreneurship, product strategy, market research, MVP planning.
```

## Where this fits in README.md

This replaces the current "Currently Building" section (`README.md` lines
37-43: the heading plus four one-line bullets) in place, between the
existing `---` after "About Me" (line 35) and the existing `---` before
"Tech Stack" (line 44) — both of those surrounding dividers stay untouched.
Within the replacement content itself, each project block ends with its own
`---` divider *except* the last one (GLIP), so the new content flows
straight into the untouched pre-existing `---` before "Tech Stack" without
a duplicate divider.

## Out of scope

- The main "Tech Stack" section (DevIcon grid) is unchanged — not part of
  this request.
- No new icons for VS Code or Cypher (both confirmed unavailable in the
  icon service; documented above rather than worked around).
- No other README sections change.
