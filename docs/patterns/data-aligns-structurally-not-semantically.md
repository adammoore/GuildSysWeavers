---
layout: page
title: "Pattern: Data Aligns Structurally but Not Semantically"
---

# When the data aligns structurally but not semantically

## Context

Two or more systems exchange data using fields, schemas, or formats that appear compatible. The data transfers successfully. No errors are raised. But the meaning of the data is different in each system, causing silent inconsistencies, incorrect processing, or downstream failures that are difficult to trace.

## Problem

Structural alignment — matching field names, data types, and formats — creates a false confidence that systems understand each other. When the semantic meaning diverges (what a field actually represents, what values mean, what assumptions are embedded), the integration appears to work while producing incorrect results.

## Forces

- Systems are often integrated based on field-level mapping without deep analysis of meaning
- Documentation of data semantics is frequently incomplete, outdated, or absent
- Different teams may use the same term to mean different things (see also: [same term, different meanings](same-term-different-meanings))
- Integration testing often verifies that data transfers, not that it means the right thing
- Semantic mismatches may only surface in edge cases or under specific conditions

## Warning signs

- Reports from different systems give different numbers for what should be the same metric
- Downstream processes produce unexpected results that are difficult to explain
- Data migration projects reveal that "equivalent" fields contain different things
- Users in different teams have different understandings of what a shared field means
- Edge cases produce absurd results (negative quantities, impossible dates, circular references)

## Anti-patterns / common bad fixes

- **Mapping fields by name alone** — assuming that fields with the same name contain the same kind of data
- **Adding transformation rules without understanding the root divergence** — patching symptoms rather than resolving the semantic difference
- **Documenting the mapping but not the meaning** — recording which fields connect without recording what they mean in each context
- **Ignoring small discrepancies** — treating minor data mismatches as acceptable noise when they indicate a fundamental semantic gap

## Better approaches

- **Map semantics, not just structure.** For each data element that crosses a system boundary, document what it means in each system, not just its format and field name.
- **Create a shared data dictionary** for cross-system data elements, explicitly noting where definitions diverge.
- **Test with meaning, not just transfer.** Integration tests should verify that data means the right thing in the receiving system, not just that it arrived.
- **Involve domain experts from both sides.** Semantic alignment requires people who understand what the data means in each context, not just how it is stored.
- **Accept and document irreconcilable differences.** Sometimes two systems genuinely mean different things. Documenting this explicitly is better than pretending alignment.

## Example scenario

Two organisations merge their HR systems. Both have a "department" field. The data migrates cleanly — field names match, data types match, no errors. But in Organisation A, "department" reflects the current budget holder; in Organisation B, it reflects the physical location. Reports built on the merged data produce nonsensical headcounts because the field means fundamentally different things. A Systems Weaver identifies the semantic divergence, creates a mapping document, and works with both teams to establish a shared definition going forward.

## Related patterns

- [When teams use the same term for different things](same-term-different-meanings)
- [When reporting outputs hide broken joins upstream](reporting-hides-broken-joins)
