# Alster Built

A personal development org. Part portfolio, part workshop.

My background is in frontend development — React, TypeScript, and the kind of
UX-focused engineering that makes complex systems feel workable. What you'll
find here reflects how I build: opinionated by design, so I'm not relitigating
the same decisions across every project.

I use Claude Code as a collaborator throughout. That's not a footnote — it
shapes how I approach architecture, iteration, and documentation.

## Infrastructure

### `frontend`

Shared foundation for building AI-forward applications. Three independent packages:

| Package | Description |
|---|---|
| `@alster-built/field-types` | Zero-React. Pure TypeScript types and validation for dynamic field definitions. |
| `@alster-built/field-renderer` | Stateless React/MUI rendering layer. Consumes field-types, renders nothing opinionated. |
| `@alster-built/ui-kit` | Theme and layout components. Independent of the field system. |

The field system is built for applications where form structure can't be known
at build time — where the shape of the UI arrives at runtime, not compile time.
That matters in AI applications. It's why it exists.

### `claude-skills`

Claude Code skill definitions used across projects — reusable context
scaffolding for common patterns so the collaboration starts from a shared
foundation instead of scratch.

## Applications

### `bayes-studio`
A general-purpose Bayesian network authoring, debugging, and inference tool.
Build networks visually, define conditional probability tables, set evidence,
run inference, and surface domain-specific annotations — all in the browser.

### `bokeh-dx` *(coming soon)*
A proof of concept using a Bayesian network to assist with clinical assessments.

## A note on scope

Backends here are functional, not precious. Production-grade architecture is
not the goal. The goal is clear, usable frontend systems — and a record of how
I think and build.

## Access

Repos are private. Case studies and writeups for projects in this org
will be published at mechaffin.github.io.

---

[Mary Ellen Chaffin](https://mechaffin.github.io/) · Clear systems, usable experiences
