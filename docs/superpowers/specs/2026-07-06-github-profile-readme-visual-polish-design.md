# GitHub Profile README — Visual Polish Design

Date: 2026-07-06

## Goal

Make the `sina-paslar` profile README more visually appealing, taking
[github.com/Danialsamadi](https://github.com/Danialsamadi) as inspiration,
while staying "tasteful" rather than template-heavy. Builds directly on top of
the current trimmed README (see
`2026-07-06-github-profile-readme-design.md`).

## Decisions (agreed with user)

- **Degree of styling:** "Tasteful polish" — centered header, DevIcon logo
  grid for the tech stack, one animated element; NOT a full decorative
  overhaul with widget-soup.
- **Header:** centered, with an animated typing SVG (readme-typing-svg)
  cycling four roles below the name.
- **Stats widgets:** intentionally omitted. The `github-readme-stats`
  vercel demo instance was down (503 DEPLOYMENT_PAUSED) earlier today; the
  polish comes from layout + icon grid, not stats cards.
- **Extra visual content:** a **snake contribution animation** (Platane/snk),
  self-hosted in the repo via a GitHub Action — chosen over trophy/banner
  add-ons because it is reliable (not a flaky external vercel host) once
  generated.
- **Retained from prior design:** the `class SinaPaslar` Python block
  (verbatim), COBOL and PHP in Languages, the "Currently Building" bullets,
  and the closing quote.

## Reliability notes

- **Typing SVG** — served from `readme-typing-svg.demolab.com`. External
  image, but a stable, widely used service. One dependency, low risk.
- **DevIcon SVGs** — served from the jsDelivr CDN
  (`cdn.jsdelivr.net/gh/devicons/devicon`). Stable CDN; each icon is a
  static SVG file.
- **COBOL has no DevIcon logo** — it stays a small shields.io text badge
  inline in the Languages row, the one exception to the icon grid.
- **Snake animation** — will render as a **broken image until the workflow
  runs at least once** and creates the `output` branch. The workflow
  includes `workflow_dispatch` (manual run) and a `push` trigger so it can
  be generated immediately after merge from the Actions tab. Once generated,
  the SVG is served from `raw.githubusercontent.com` off the repo's own
  `output` branch — no third-party runtime dependency.

## Files

- Modify: `README.md` (full replacement with the layout below)
- Create: `.github/workflows/snake.yml` (generates the snake SVG)

## Final README content

```markdown
<div align="center">

# Hi, I'm Sina Paslar 👋

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=1000&center=true&vCenter=true&width=520&lines=Full-Stack+Developer;Python+Developer;Database+%26+Graph+Systems;Entrepreneur)](https://github.com/Sina-Paslar)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sina%20Paslar-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/sina-paslar/)
[![GitHub](https://img.shields.io/badge/GitHub-sina--paslar-black?style=flat-square&logo=github)](https://github.com/Sina-Paslar)
[![Email](https://img.shields.io/badge/Email-sina83paslar%40gmail.com-red?style=flat-square&logo=gmail)](mailto:sina83paslar@gmail.com)

</div>

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

**Languages**
<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="45" height="45" alt="Python" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" width="45" height="45" alt="TypeScript" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" width="45" height="45" alt="JavaScript" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" width="45" height="45" alt="Java" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg" width="45" height="45" alt="Go" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" width="45" height="45" alt="PHP" />
  <img src="https://img.shields.io/badge/COBOL-005CA5?style=for-the-badge" height="28" alt="COBOL" />
</p>

**Frontend**
<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="45" height="45" alt="React" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" width="45" height="45" alt="Next.js" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg" width="45" height="45" alt="Tailwind CSS" />
</p>

**Backend & Databases**
<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/supabase/supabase-original.svg" width="45" height="45" alt="Supabase" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" width="45" height="45" alt="PostgreSQL" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/neo4j/neo4j-original.svg" width="45" height="45" alt="Neo4j" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" width="45" height="45" alt="MongoDB" />
</p>

**Tools**
<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" width="45" height="45" alt="Git" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="45" height="45" alt="Docker" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" width="45" height="45" alt="VS Code" />
</p>

---

## Contribution Activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Sina-Paslar/sina-paslar/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Sina-Paslar/sina-paslar/output/github-contribution-grid-snake.svg" />
  <img alt="Snake eating my contribution graph" src="https://raw.githubusercontent.com/Sina-Paslar/sina-paslar/output/github-contribution-grid-snake.svg" />
</picture>

</div>

---

> Clean structure. Practical features. Real user value.
```

## Workflow file content (`.github/workflows/snake.yml`)

```yaml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 0 * * *"   # daily
  workflow_dispatch:        # manual run button
  push:
    branches: [main]

jobs:
  generate:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## Post-merge steps (manual, by the user)

1. After merge to `main`, open the repo's **Actions** tab.
2. Run the "Generate Snake Animation" workflow via **Run workflow**
   (workflow_dispatch), or wait for the daily schedule.
3. Confirm the `output` branch is created and the snake SVGs exist there.
4. The README's Contribution Activity image will then render.

## Out of scope

- Stats/trophy/banner widgets (explicitly declined).
- Any change to repository code other than `README.md` and the new workflow.
