---
layout: page
title: "Pattern: Reporting Hides Broken Joins"
---

# When reporting outputs hide broken joins upstream

## Context

Reports, dashboards, or data outputs present clean, aggregated, or visualised data to decision-makers. The outputs look correct and authoritative. But the data pipeline feeding them involves broken joins, incomplete integrations, silent failures, or manual corrections that the report consumer has no way to see.

## Problem

Reporting is typically the most visible layer of a data pipeline. When reports look clean, there is a strong tendency to assume the underlying data is healthy. But reports can hide — through aggregation, formatting, default values, or simply by not showing what is missing — a wide range of upstream problems. Decisions are then made on data that is incomplete, inconsistent, or wrong in ways that the report does not reveal.

## Forces

- Reports aggregate data, which can smooth over inconsistencies visible at the row level
- Missing data may appear as zero rather than as an error
- Report consumers are rarely in a position to question the data pipeline
- The further data travels from its source, the harder it is to trace problems
- Pressure to produce reports on schedule discourages thorough investigation of data quality
- Dashboard aesthetics can create a false sense of precision and reliability

## Warning signs

- Reports show slightly different numbers depending on who runs them or when
- Data quality issues are reported by operational staff but do not appear in management dashboards
- Manual corrections are applied to data before it reaches the reporting layer
- The reporting pipeline has error handling that substitutes default values for missing data
- No one can explain the full data lineage from source to report
- Report numbers do not match the experience of people working with the underlying systems

## Anti-patterns / common bad fixes

- **Making the report look better** — formatting, rounding, or adjusting outputs to hide anomalies rather than investigating them
- **Adding caveats in footnotes** that no one reads instead of fixing the underlying data problem
- **Building a new report** that draws from a different data source to avoid the known problems, creating parallel sources of truth
- **Blaming the reporting tool** when the problem is in the data pipeline

## Better approaches

- **Trace the data lineage.** For every key metric in a report, document where the data comes from, what transformations it undergoes, and where it crosses system boundaries. This is often the single most revealing exercise.
- **Make data quality visible in the report itself.** Include indicators of completeness, freshness, and known issues alongside the data. Decision-makers can then judge how much to trust the numbers.
- **Monitor the pipeline, not just the output.** Checks should exist at each stage of the data pipeline — not just at the point of report generation.
- **Investigate discrepancies rather than smoothing them over.** When two sources give different numbers for the same thing, that difference contains important information about the state of the integration.
- **Involve report consumers in data quality conversations.** The people making decisions based on reports should understand the limitations of the data, not just the numbers.

## Example scenario

A regional health authority's performance dashboard shows hospital wait times aggregated by area. The dashboard looks clean and is used for resource allocation decisions. But the data pipeline joining three different hospital systems has a silent failure: one hospital's data feed stopped working six weeks ago, and the pipeline's error handling substitutes the last known values rather than flagging the missing data. The dashboard continues to show wait times for that hospital — they just have not changed in six weeks, a fact obscured by the aggregation. A Systems Weaver investigates a discrepancy reported by a ward manager, traces the data lineage, discovers the broken feed, and implements pipeline monitoring with explicit freshness checks that surface in the dashboard as data confidence indicators.

## Related patterns

- [When the data aligns structurally but not semantically](data-aligns-structurally-not-semantically)
- [When no single system owns the whole process](no-single-system-owns-the-process)
- [When automation obscures responsibility](automation-obscures-responsibility)
