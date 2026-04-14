---
layout: page
title: "Pattern: The API Exists but the Organisation Does Not"
---

# When the API exists but the organisation does not

## Context

A technical integration between systems has been built. APIs exist, data flows, and the technical connection works. But the organisational structures needed to support, maintain, and govern the integration — ownership, processes, agreements, escalation paths — do not exist or have not kept pace with the technical implementation.

## Problem

Technical integrations require ongoing organisational support: someone to be responsible when things break, processes for making changes, agreements about data quality and availability, and governance for how the integration evolves. When the technical connection exists without this organisational scaffolding, the integration is fragile, ungoverned, and tends to fail in ways that no one is equipped to resolve.

## Forces

- Technical teams can build integrations faster than organisations can create governance for them
- Project-funded integrations often lack ongoing operational ownership
- APIs are treated as technical artefacts rather than organisational agreements
- The team that built the integration may not be the team that operates it
- Integration governance is frequently seen as overhead rather than essential infrastructure

## Warning signs

- No one can name who is responsible for the integration
- Changes to either connected system break the integration with no prior coordination
- There is no process for communicating planned downtime or changes
- Data quality issues in the integration are reported but never resolved
- The integration was built by a project team that has since disbanded
- There is no service level agreement or shared understanding of expected behaviour

## Anti-patterns / common bad fixes

- **Treating the API as self-sufficient** — assuming that because the technical interface exists, no human coordination is needed
- **Assigning ownership to the team that built it** rather than the team that needs it — the building team may lack ongoing context or motivation
- **Creating governance documents without governance practice** — writing an integration agreement that no one reads or maintains
- **Escalating every issue to senior management** because there is no operational-level owner or process

## Better approaches

- **Establish a named integration owner** — a person or team responsible for the health, performance, and evolution of the integration. This is distinct from owning either connected system.
- **Create a lightweight integration agreement** that documents: what data flows, in what direction, with what expectations, who to contact when something breaks, and how changes are coordinated.
- **Build communication channels** between the teams on either side of the integration. Regular contact prevents surprises.
- **Include integration health in operational reviews.** If no one is monitoring the integration's behaviour, problems will accumulate silently.
- **Plan for the integration's lifecycle.** It will need maintenance, updates, and eventually replacement. These need budget, time, and people.

## Example scenario

A healthcare organisation integrates its patient records system with a laboratory results system via an API built during a digital transformation project. The API works, results flow. The project team moves on. Six months later, a schema change in the laboratory system silently corrupts data in the patient records. No one notices for weeks because no one owns the integration and no monitoring exists. A Systems Weaver identifies the gap, establishes an integration owner from the operations team, creates a monitoring check, and drafts a lightweight agreement between the two teams about change notification and data quality expectations.

## Related patterns

- [When no single system owns the whole process](no-single-system-owns-the-process)
- [When automation obscures responsibility](automation-obscures-responsibility)
