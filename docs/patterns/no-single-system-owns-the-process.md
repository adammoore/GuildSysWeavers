---
layout: page
title: "Pattern: No Single System Owns the Process"
---

# When no single system owns the whole process

## Context

A business process or service delivery workflow spans multiple systems, each of which handles a portion of the work. No single system — and no single team — has end-to-end visibility or responsibility for the process as a whole.

## Problem

When a process crosses system boundaries, the gaps between systems become invisible failure points. Each team sees their part working correctly, but the overall process is fragile, inconsistent, or broken. Errors, delays, and data loss occur at handoff points that no one formally owns.

## Forces

- Each system was designed and procured independently, often at different times and by different teams
- Ownership boundaries follow system boundaries, not process boundaries
- No one has the mandate, budget, or visibility to manage the end-to-end flow
- Performance metrics measure system uptime, not process completion
- Users experience the process as one thing; the organisation manages it as many

## Warning signs

- Users report problems that no single team can reproduce
- "It works on our end" is a common response between teams
- Incidents take disproportionately long to diagnose because they involve multiple teams
- Data arrives in the wrong state or sequence at downstream systems
- Manual workarounds exist at system boundaries that are known to few people
- No one can draw the actual end-to-end process on a whiteboard

## Anti-patterns / common bad fixes

- **Building a "master system"** that tries to orchestrate everything, creating a new single point of failure and ownership confusion
- **Creating yet another dashboard** that aggregates data from all systems but has no ability to affect the actual process
- **Assigning an "owner" on paper** without giving them authority, tooling, or time to actually manage the process
- **Ignoring the gaps** because each team's system is technically functioning correctly

## Better approaches

- **Map the actual process flow** across all systems, including manual steps, workarounds, and informal handoffs. The map itself is a valuable deliverable.
- **Identify and document the handoff points** — what data or state transfers between systems, in what form, with what assumptions, and what happens when it fails.
- **Establish cross-boundary monitoring** that tracks the process, not just the systems. This might be as simple as a shared log or as sophisticated as a correlation ID.
- **Create explicit ownership for boundary points** — even if no one owns the whole process, someone should own each join between systems.
- **Design graceful failure at handoffs** — what happens when a handoff fails should be defined, not discovered in production.

## Example scenario

A university's student enrolment process spans four systems: the application portal, the admissions system, the student records system, and the finance system. Each is maintained by a different team. When a student's enrolment fails, it takes days to diagnose because the failure occurred at the handoff between admissions and student records — a point managed by no one. A Systems Weaver maps the actual end-to-end flow, documents the handoff specifications, and establishes a shared monitoring approach, turning an invisible failure mode into a managed boundary.

## Related patterns

- [When the workflow depends on one person's memory](workflow-depends-on-one-persons-memory)
- [When reporting outputs hide broken joins upstream](reporting-hides-broken-joins)
- [When automation obscures responsibility](automation-obscures-responsibility)
