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

A platform for reasoning under uncertainty, built as a domain-pluggable DSL
over a Bayesian computation graph (with some extensions). Authors encode
domain knowledge in the DSL; practitioners, reviewers, and trainees consume
it through role-specific workflows.

Five activities are supported: authoring, using in practice, reviewing
reasoning, training practitioners, and measuring reasoning quality. Domain
packages provide network structure, annotation content, training cases, and
workflow definitions. The first real
domain package is **bokeh-dx** (mental health mood disorder differential
diagnosis). Five demo domains exercise the platform against bare networks of
varying size and shape: the classic **Asia** (Lauritzen & Spiegelhalter) and
**rain-sprinkler** (Pearl) reference networks, **HEPAR II** liver disease
(Oniśko et al.), plus automotive troubleshooting and insurance risk.

Inference runs as a `nodalyze`-owned service (`packages/bayes` for the
pgmpy engine, `packages/app/src/services/bayesClient.ts` for the typed TS
client) so each domain owns its own inference rather than sharing
infrastructure.

## Applications

### `model-card-studio`

A chat-driven editor for authoring ML model cards. Users converse with
an assistant that asks structured questions, proposes field values, and
renders inline forms where input is needed; the current card stays
visible in a side panel and exports as markdown or JSON. Built on
`@alster-built/ui-kit`, `core`, and `backend-client`.

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

A shared backend supporting alster-built frontend applications. Hosts the
Claude AI proxy: SSE streaming, tool use, and Anthropic API key
containment so the key never leaves the server. Includes a TypeScript
client package (`@alster-built/backend-client`) for compile-time safety.

### `claude-toolkit`

A Claude Code plugin bundling shared skills and slash commands for the
alster-built ecosystem. Installed once per developer machine via
`/plugin install claude-toolkit@alster-built`; edits in the working tree
are live across every project. Skills are opinionated, prescriptive, and
portable — they encode decisions, not menus. Coverage spans code,
research, writing, and utility workflows, with skills composed into
named pipelines (e.g., research brief → pipeline scaffold → deep
research → paper).

### `research-projects`

Organized research projects that inform development decisions across the org.
Each project synthesizes academic and technical literature with explicit
sourcing. Output feeds design documents, specifications, and domain expertise.

## Access

Repos are private. Case studies and writeups for projects in this org
will be published at mechaffin.github.io.

---

[Mary Ellen Chaffin](https://mechaffin.github.io/) · Clear systems, usable experiences
