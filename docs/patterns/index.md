---
layout: page
title: Patterns
permalink: /patterns/
---

The pattern library documents recurring situations that Systems Weavers encounter in cross-boundary infrastructure work. Each pattern describes a recognisable problem, its context, common failed approaches, and better strategies.

These patterns are drawn from real practice. They are deliberately practical — not theoretical frameworks, but descriptions of situations that practitioners will recognise from their own experience.

## How patterns are structured

Each pattern follows a standard template:

- **Context** — the situation in which the pattern arises
- **Problem** — what goes wrong
- **Forces** — the dynamics that create and sustain the problem
- **Warning signs** — how to recognise the pattern
- **Anti-patterns / common bad fixes** — what usually makes it worse
- **Better approaches** — what experienced practitioners do instead
- **Example scenario** — a concrete (anonymised) illustration
- **Related patterns** — connections to other patterns in the library

## Current patterns

### Boundary and ownership

- [When no single system owns the whole process](no-single-system-owns-the-process) — processes that cross system boundaries with no end-to-end ownership
- [When the API exists but the organisation does not](api-exists-but-organisation-does-not) — technical integrations without organisational scaffolding

### Data and semantics

- [When the data aligns structurally but not semantically](data-aligns-structurally-not-semantically) — matching schemas that mask divergent meaning
- [When teams use the same term for different things](same-term-different-meanings) — shared vocabulary without shared understanding

### Knowledge and process

- [When the workflow depends on one person's memory](workflow-depends-on-one-persons-memory) — critical processes sustained by undocumented individual knowledge
- [When manual work is carrying architectural debt](manual-work-carrying-architectural-debt) — human labour absorbing systemic failures

### Visibility and accountability

- [When automation obscures responsibility](automation-obscures-responsibility) — automated processes with unclear accountability
- [When reporting outputs hide broken joins upstream](reporting-hides-broken-joins) — clean reports built on broken data pipelines

## Contributing a pattern

If you have encountered a recurring situation in cross-boundary work that is not yet documented here, we welcome contributions. See the [pattern template](https://github.com/adamvialsmoore/GuildSysWeavers/blob/main/templates/pattern-template.md) and [contribution guide](https://github.com/adamvialsmoore/GuildSysWeavers/blob/main/CONTRIBUTING.md), or [open an issue](https://github.com/adamvialsmoore/GuildSysWeavers/issues/new?template=new-pattern.yml) to discuss a pattern idea.
