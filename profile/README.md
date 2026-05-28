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

A platform for decision-support applications in domains where the
reasoning behind a decision has to be defensible — inspectable,
reproducible, attributable to a source. Built on Bayesian networks,
with a domain-pluggable DSL that lets experts encode their reasoning
once and practitioners consume it through role-specific workflows.
Case studies are in progress.

## Applications

### `form-filler-studio`

A chat-driven editor for authoring structured documents from a schema
pack. Users converse with an assistant that asks structured questions,
proposes field values, and renders inline forms where input is needed;
the current document stays visible in a side panel and exports as
markdown or JSON. New document types plug in as packs — a schema, an
option set, and a markdown renderer — without touching the app shell.
Built on `frontend`, and `backend-client`.

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
will be published at [mechaffin.github.io/blog](https://mechaffin.github.io/blog).

---

[Mary Ellen Chaffin](https://mechaffin.github.io/) · Clear systems, usable experiences
