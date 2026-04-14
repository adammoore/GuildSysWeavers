---
layout: page
title: "Pattern: Workflow Depends on One Person's Memory"
---

# When the workflow depends on one person's memory

## Context

A critical process or workflow functions correctly, but its operation depends on knowledge held by a single person — knowledge that is not documented, not shared, and often not recognised by the organisation as existing.

## Problem

Organisations build formal systems and processes but routinely underestimate how much operational continuity depends on specific individuals' undocumented knowledge. When that person is absent, moves on, or retires, the workflow breaks in ways that are difficult to diagnose because the knowledge gap is invisible.

## Forces

- Formal documentation describes the intended process, not the actual process including workarounds
- The person with the knowledge may not realise how unique their understanding is
- Organisations often cannot see single points of knowledge failure until they fail
- The knowledge is typically procedural and contextual — it does not fit neatly into a document
- The person may be valued precisely because of their indispensability, creating a disincentive to share

## Warning signs

- One person is always consulted when something goes wrong with a particular process
- "Only Sarah knows how that works" is said without alarm
- Holiday or sick leave by specific individuals causes disproportionate disruption
- The process has undocumented manual steps that are not reflected in any system
- New team members take unusually long to become effective in certain areas
- There are recurring incidents that only one person can resolve

## Anti-patterns / common bad fixes

- **Demanding the person "document everything"** without providing time, support, or a useful format — documentation created under duress is rarely usable
- **Assuming the formal documentation is sufficient** — if the process works differently from the documentation, the documentation is not the knowledge
- **Replacing the person with automation** before understanding what they actually do — automating the documented process misses the undocumented parts
- **Cross-training by shadowing** without structured knowledge capture — watching someone work does not reliably transfer tacit knowledge

## Better approaches

- **Walk the actual process with the person.** Have them narrate what they do, including the steps they consider too obvious to mention. Those are usually the critical ones.
- **Document decisions, not just steps.** The valuable knowledge is often about when to deviate from the standard process, what exceptions exist, and why certain things are done in a particular way.
- **Create runbooks for the non-obvious.** Focus documentation effort on the parts of the process that are not captured in any system — the manual checks, the sequencing requirements, the "if this then that" knowledge.
- **Build in redundancy gradually.** Pair the knowledge-holder with another person on a regular basis, not just as a one-off documentation exercise.
- **Acknowledge the knowledge.** Often the first step is making the organisation aware that this knowledge exists and is critical. The person may be doing invisible work that the organisation relies on without realising it.

## Example scenario

A council's monthly reporting process technically runs through an automated pipeline, but every month the same data analyst manually checks three specific fields, corrects values that the system misinterprets due to a known legacy issue, and sequences the final upload in a particular order because two downstream systems have an undocumented dependency. When the analyst takes extended leave, the reports fail in three different ways. A Systems Weaver works with the analyst to document the actual process, identifies the legacy data issue and the sequencing dependency, and creates a runbook that allows others to operate the process.

## Related patterns

- [When no single system owns the whole process](no-single-system-owns-the-process)
- [When manual work is carrying architectural debt](manual-work-carrying-architectural-debt)
