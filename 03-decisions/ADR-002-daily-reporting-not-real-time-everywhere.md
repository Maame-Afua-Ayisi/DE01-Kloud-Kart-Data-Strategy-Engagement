# ADR-002: Use daily refreshes for business reporting, not real-time reporting everywhere

- Status: Proposed — pending approval
- Date: 2026-11-12
- Decision owner: Kloud Kart leadership, with requirements input from Operations and Finance

## Context

Kloud Kart has been asked by investors about data strategy and real-time analytics. However, the case states that stock counts cannot become stale while everything else can refresh daily. The business currently spends time rebuilding Monday reports, and reporting activity has affected the live website.

A blanket real-time reporting programme would increase technical complexity and cost without evidence that every business measure needs continuous updates.

## Decision

Use daily refreshes for routine business reports such as revenue, order performance, customer and operational reporting. Treat live stock availability and stock-changing transactions as a separate operational requirement and keep them on the primary application database.

Any future real-time reporting requirement must be justified by a specific business decision, an agreed freshness requirement and an assessment of its cost and operational impact.

## Alternatives considered

### Alternative A: Build real-time dashboards for all business measures

- How it would work: Continuously update dashboards or query operational data so that revenue, orders, customers, stock and other measures appear close to real time.
- Why it is attractive: It responds visibly to investor interest and provides frequently updated information.
- Why rejected: The case only establishes a strict freshness requirement for stock. Real-time reporting across all measures would add complexity and could recreate the load and reliability problems the strategy is intended to remove.

### Alternative B: Refresh every report weekly

- How it would work: Keep a weekly reporting cycle similar to the current Monday export process.
- Why it is attractive: It is simpler to operate and would require fewer scheduled refreshes.
- Why rejected: Daily reporting is a more useful improvement for management visibility and reduces reliance on repeated manual weekly exports. The case permits daily refreshes for non-stock information.

## Consequences

- What this buys: A reporting schedule aligned with actual business needs, lower complexity than real-time reporting everywhere, and a clear distinction between analytical reporting and live stock operations.
- What this costs: Some dashboards will not show changes immediately. Users must understand that daily reports are not live operational views.
- What it costs the client if I am wrong: If a business process later requires faster information than the daily refresh provides, decisions may be made using data that is not current enough.
- What would make me revisit this: A documented business requirement for faster updates, evidence that daily refreshes delay an important decision, or a change in stock-management requirements.

## What this survives

This decision survives investor pressure for real-time analytics because it does not reject real-time capability altogether; it limits it to use cases where freshness matters. It also survives growth in order volume by avoiding unnecessary continuous reporting workloads. If a specific real-time use case emerges, Kloud Kart can assess and fund it separately rather than redesigning every report.
