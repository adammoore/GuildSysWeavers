---
layout: page
title: "Pattern: Manual Work Carrying Architectural Debt"
---

# When manual work is carrying architectural debt

## Context

People are performing regular manual work — data corrections, format conversions, reconciliations, copy-paste between systems, manual checks — that compensates for limitations or failures in the underlying systems architecture.

## Problem

What appears to be a staffing or efficiency problem is actually an architecture problem. The manual work exists because systems do not connect properly, data models do not align, or process automation is incomplete. The people doing this work are not inefficient — they are absorbing complexity that the systems should be handling but do not.

## Forces

- Manual workarounds accumulate gradually and become normalised
- The people doing the work may not realise that what they do is compensating for architectural failure
- The cost of the manual work is visible (staff time) but its cause is hidden (architectural gaps)
- Proposals to automate often focus on the manual task rather than fixing the underlying architecture
- Fixing the architecture is expensive and disruptive; continuing the manual work seems cheaper in the short term

## Warning signs

- Staff spend significant time on repetitive tasks that involve moving data between systems
- Spreadsheets serve as the integration layer between formal systems
- The same data is manually entered into multiple systems
- Staff have developed personal tools, scripts, or checklists for tasks that should be systemic
- When asked why they do a particular task, staff say "it's always been done this way" or "the system doesn't handle it"
- New staff require extensive training in workarounds that are not documented in any system

## Anti-patterns / common bad fixes

- **Automating the workaround** rather than fixing the root cause — building an automated script that copies data between systems every night instead of fixing the integration
- **Hiring more people** to handle increasing manual volume without questioning why the volume exists
- **Blaming staff for inefficiency** when they are compensating for systemic failures
- **Removing the manual work without replacing its function** — if the workaround is removed but the architectural gap remains, things will break

## Better approaches

- **Map the manual work to the architectural gap it compensates for.** This makes visible the real cost and cause of the work.
- **Quantify the work.** How many hours per week, month, or year are spent on this? What would happen if it stopped? This creates a business case for fixing the architecture.
- **Distinguish between work that could be eliminated and work that needs to be preserved.** Some manual intervention reflects genuine judgement; some is pure data plumbing. The response should be different for each.
- **Fix the architecture incrementally.** Full architectural redesign is often impractical. Identify the highest-impact gaps and address them first.
- **Honour the knowledge.** The people doing the manual work understand the failures better than anyone. Their knowledge should inform the architectural fix, and their contribution should be recognised.

## Example scenario

A research institution's grants management process requires a team of three administrators to manually reconcile financial data between the grants system, the finance system, and the research reporting system every month. Each system uses different cost categories, different project identifiers, and different reporting periods. The administrators have developed an elaborate set of spreadsheets to bridge the gaps. A Systems Weaver documents the reconciliation process, maps each manual step to the specific architectural mismatch it compensates for, and presents the total annual cost. This leads to a targeted integration project that addresses the three highest-impact gaps, reducing manual effort by 60% and improving data quality.

## Related patterns

- [When the workflow depends on one person's memory](workflow-depends-on-one-persons-memory)
- [When no single system owns the whole process](no-single-system-owns-the-process)
- [When automation obscures responsibility](automation-obscures-responsibility)
