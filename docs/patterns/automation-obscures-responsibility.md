---
layout: page
title: "Pattern: Automation Obscures Responsibility"
---

# When automation obscures responsibility

## Context

A process that previously involved visible human decisions has been automated. The automation works, but it has made it unclear who is responsible for the outcomes — including errors, exceptions, and edge cases that the automation handles silently or incorrectly.

## Problem

Automation is often introduced to reduce manual effort and increase consistency, which it can do well. But when automation replaces human decision-making without preserving clear accountability for the process and its outcomes, responsibility becomes diffused. Errors that a human would have noticed and escalated are now handled — or mishandled — invisibly.

## Forces

- Automation is typically designed for the common case, not the exception
- The people who built the automation may not be the people accountable for the process
- Automated processes are harder to audit than manual ones because decisions are embedded in code
- Automation can create the illusion that a problem has been solved when it has merely been hidden
- Responsibility that was previously carried by a person is often not formally reassigned when automation takes over

## Warning signs

- No one can explain who is responsible when the automated process produces a wrong outcome
- Exceptions are silently dropped, queued indefinitely, or processed incorrectly
- The automation has not been updated to reflect changes in business rules or upstream systems
- Users trust the output because "the system does it" without understanding what the system actually does
- There is no process for reviewing or auditing the automation's decisions
- When the automation fails, the response is to restart it rather than investigate why

## Anti-patterns / common bad fixes

- **Treating automation as self-governing** — assuming that once automated, a process needs no human oversight
- **Adding more automation to handle failures in existing automation** — creating layers of automated processes that no one fully understands
- **Assigning responsibility to the automation itself** — "the system decided" is not accountability
- **Removing all human touchpoints** — some decisions need human judgement, and automating them away does not eliminate the need for judgement, it just hides it

## Better approaches

- **Maintain clear ownership.** Every automated process should have a named person or team responsible for its outcomes — including its failures.
- **Design for exceptions, not just the happy path.** What happens when the automation encounters something it was not designed for? The answer should be explicit, not left to chance.
- **Build in visibility.** Automated processes should produce logs, alerts, and audit trails that make their decisions visible and reviewable.
- **Preserve human checkpoints** for high-consequence decisions. Automation should assist human decision-making, not invisibly replace it.
- **Review automation regularly** against current business rules and upstream changes. Automation encodes assumptions that may no longer be valid.

## Example scenario

A financial services firm automates its client onboarding checks. The system verifies identity, runs compliance checks, and approves applications. It works well for standard cases. But a regulatory change adds a new check that the automation does not account for. Non-compliant applications are approved for three months before an audit discovers the gap. No one is responsible for reviewing the automation against regulatory changes because when the process was manual, the compliance team reviewed each application; when it was automated, that responsibility was not explicitly reassigned. A Systems Weaver maps the accountability chain, identifies the gap, establishes a review process, and creates monitoring for the automation's decision outputs.

## Related patterns

- [When no single system owns the whole process](no-single-system-owns-the-process)
- [When manual work is carrying architectural debt](manual-work-carrying-architectural-debt)
- [When the API exists but the organisation does not](api-exists-but-organisation-does-not)
