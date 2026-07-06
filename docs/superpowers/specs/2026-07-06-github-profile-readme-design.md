# GitHub Profile README Redesign

Date: 2026-07-06

## Goal

Redesign `README.md` (the GitHub profile README for `sina-paslar`) so it reads
in well under 30 seconds while keeping the personal "Python class" bio touch.
Current version is thorough but long: 4 detailed project write-ups, a 6-row
tech table, a strengths table, two stats images, and a separate contact
section that duplicates header links.

## Research basis

- Profile READMEs work best as a landing page, not documentation: sharp bio,
  current work, one stats widget, featured projects with one-liners, one way
  to reach you.
- Avoid: animated GIFs/flashy effects, exhaustive tech lists, visitor
  counters, duplicated content (e.g. links in both header and footer).
- Prefer badge rows over tables for tech stacks — scans faster, reads as more
  current.

## Structure (agreed with user)

1. **Header** — name, role tagline, badge row (LinkedIn, GitHub, email)
2. **About Me** — keep the existing `class SinaPaslar` Python code block
   as-is (user explicitly wants this kept)
3. **Currently Building** — 3-4 one-line bullets (project name + what it is +
   primary stack), replacing the 4 detailed paragraph sections
4. **Tech Stack** — badge rows grouped by category (Languages, Frontend,
   Backend & Databases, Tools), replacing the 6-row table
5. **GitHub Stats** — one stats widget only (contributions/streak), the
   top-languages image is dropped as redundant with the badge row
6. **Connect** — dropped as a standalone section; links live in the header
   badge row only (dedupe)

Dropped from current version: the "Core Strengths" table and the "Project
Philosophy" quote block (both are personality/tone content covered already by
the shorter bio and bullets — reintroducing them would undercut the scannability
goal). The 4 detailed project sections collapse into one-line bullets under
"Currently Building."

## Final content

```markdown
# Hi, I'm Sina Paslar 👋

**Junior Software Developer | Full-Stack & Python Developer | Entrepreneur**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sina%20Paslar-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/sina-paslar/)
[![GitHub](https://img.shields.io/badge/GitHub-sina83paslar-black?style=flat-square&logo=github)](https://github.com/Sina-Paslar)
[![Email](https://img.shields.io/badge/Email-sina83paslar%40gmail.com-red?style=flat-square&logo=gmail)](mailto:sina83paslar@gmail.com)

---

## About Me

```python
class SinaPaslar:
    def __init__(self):
        self.role = "Junior Software Developer"
        self.education = "Computer Programming - Algonquin College"
        self.focus = [
            "Full-Stack Development",
            "Python Development",
            "Database Systems",
            "Accessibility Features",
            "AI + Graph-Based Applications",
            "Entrepreneurship"
        ]

    def working_on(self):
        return "Building practical software with strong UX, clean architecture, and real business value."
```

---

## Currently Building

- **Auspicious App** — accessibility-focused learning platform (Next.js, TypeScript, Supabase)
- **Hippodamus** — construction safety & workflow platform (Next.js, TypeScript, Supabase)
- **Course Similarity Graph** — course-comparison engine using graph relationships and LLM topic extraction (Python, Neo4j, Gemini API)
- **GLIP** — early-stage startup/product project (market research, MVP planning)

---

## Tech Stack

**Languages:** ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Java](https://img.shields.io/badge/-Java-007396?style=flat-square&logo=openjdk&logoColor=white) ![Go](https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=go&logoColor=white)

**Frontend:** ![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

**Backend & Databases:** ![Supabase](https://img.shields.io/badge/-Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Neo4j](https://img.shields.io/badge/-Neo4j-4581C3?style=flat-square&logo=neo4j&logoColor=white) ![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**Tools:** ![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white) ![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![VS Code](https://img.shields.io/badge/-VS_Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white)

---

## GitHub Stats

<p align="center">
  <img
    src="https://github-readme-stats.vercel.app/api?username=sina-paslar&show_icons=true&theme=github_dark&hide_border=true"
    alt="Sina's GitHub Stats"
  />
</p>

---

> Clean structure. Practical features. Real user value.
```

## Notes on trade-offs

- Badge images for tech stack rely on shields.io + simple-icons; same
  external-image approach already used for stats, so no new dependency class.
- Email badge added to header since the "Connect" section is being removed —
  keeps all contact info in one place.
- The closing quote line is kept (one line, not a full "Project Philosophy"
  section) as a low-cost personality touch.

## Out of scope

- No changes to repository code, only `README.md`.
- No new automation (e.g. GitHub Actions for dynamic content) — out of scope
  for this pass.
