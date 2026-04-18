# Alster Built

A personal development org. Part portfolio, part workshop.

My background is in frontend development — React, TypeScript, and the kind of
UX-focused engineering that makes complex systems feel workable. What you'll
find here reflects how I build: opinionated by design, so I'm not relitigating
the same decisions across every project.

I use Claude Code as a collaborator throughout. That's not a footnote — it
shapes how I approach architecture, iteration, and documentation.

## Platform

### `nodalyze`

A platform for structured reasoning under uncertainty. Nodalyze combines a
Bayesian network inference engine with domain-specific knowledge packages to
support five activities: authoring networks, using them in practice, reviewing
reasoning, training practitioners, and measuring reasoning quality.

The platform is domain-agnostic. Domain packages provide network structure,
annotation content, training cases, and workflow definitions. The first real
domain package is **bokeh-dx** (mental health mood disorder differential
diagnosis). Five demo domains exercise the platform against bare networks of
varying size and shape: the classic **Asia** (Lauritzen & Spiegelhalter) and
**rain-sprinkler** (Pearl) reference networks, **HEPAR II** liver disease
(Oniśko et al.), plus automotive troubleshooting and insurance risk.

## Infrastructure

### `frontend`

A domain-agnostic toolkit for building data-dense professional applications.
Two packages enforce one dependency boundary:

| Package                | Description                                                                                                          |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `@alster-built/core`   | Zero-React. Pure TypeScript types, field definitions, and validation. Consumable by backends, CLIs, and build tools. |
| `@alster-built/ui-kit` | All React/MUI rendering: field components, form renderers, app chrome, color system, markdown editing, and theme.    |

Built for data-dense, professional, information-first interfaces — not
consumer-friendly-spacious. Form structure arrives at runtime, not compile
time. The UI kit is opinionated enough that many raw `@mui/material` imports in
app code are treated as a code smell.

### `backend-services`

A shared backend supporting alster-built frontend applications. Provides
API endpoints that frontends cannot or should not run client-side:
probabilistic inference via pgmpy (posterior queries, information-gain
ranking, sensitivity analysis) and a Claude AI proxy with SSE streaming
and tool use that keeps the Anthropic API key server-side. Includes a
TypeScript client package for compile-time safety.

### `claude-skills`

A shared library of Claude Code skills for the alster-built ecosystem.
Consuming projects add it as a git submodule at `.claude/skills/` so
Claude Code picks up the skills automatically. Skills are opinionated,
prescriptive, and portable — they encode decisions, not menus. Coverage
spans code, research, writing, and utility workflows, with skills
composed into named pipelines (e.g., research brief → pipeline scaffold
→ deep research → paper).

### `research-projects`

Organized research projects that inform development decisions across the org.
Each project synthesizes academic and technical literature with explicit
sourcing. Output feeds design documents, specifications, and domain expertise.

## Access

Repos are private. Case studies and writeups for projects in this org
will be published at mechaffin.github.io.

---

[Mary Ellen Chaffin](https://mechaffin.github.io/) · Clear systems, usable experiences
