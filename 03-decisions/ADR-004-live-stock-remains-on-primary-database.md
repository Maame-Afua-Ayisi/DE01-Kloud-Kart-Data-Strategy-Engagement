# ADR-004: Keep live stock decisions on the primary MySQL database

- Status: Proposed — pending approval
- Date: 2026-11-12
- Decision owner: Kloud Kart leadership, with input from Operations and the PHP/MySQL developer

## Context

Kloud Kart's case brief states that stock counts cannot become stale, while other reporting information can refresh daily. A MySQL read replica is recommended for reporting, but replicated data can lag behind the primary database.

Stock availability and stock-changing transactions affect whether Kloud Kart can accept and fulfil an order. A delayed reporting copy must not become the authority for these live decisions.

## Decision

Keep live stock availability checks and stock-changing transactions on the primary operational MySQL database. Do not use the reporting replica or daily Power BI dashboards as the authoritative source for live stock decisions.

The replica may support historical stock movement and operational analysis, provided its freshness limitations are made clear.

## Alternatives considered

### Alternative A: Use the read replica for live stock availability checks

- How it would work: The website or another live process would read stock levels from the replica to reduce activity on the primary database.
- Why it is attractive: It could reduce read activity on the primary database and make broader use of the second server.
- Why rejected: Replication delay could cause the replica to show stock that has already been sold or changed on the primary. This creates a risk of accepting orders against stale stock information.

### Alternative B: Use the daily reporting dataset or Power BI dashboard for stock decisions

- How it would work: Staff would rely on the daily refreshed reporting view to decide whether products are available.
- Why it is attractive: It would make stock information visible in the same reporting environment as other business measures.
- Why rejected: A daily refresh is explicitly insufficient for the case's stock-freshness requirement. Dashboards are for analysis and management visibility, not authoritative transaction processing.

## Consequences

- What this buys: Live stock decisions continue to use the operational source of truth, reducing the risk of stale stock information driving order acceptance.
- What this costs: The primary database continues to handle live stock reads and writes. Its performance must still be monitored and the application queries may need optimisation.
- What it costs the client if I am wrong: If the primary database becomes overloaded, live stock checks may be slower. Keeping stock on the primary does not by itself solve every performance issue; the application and database still require appropriate monitoring and tuning.
- What would make me revisit this: A separately designed inventory service with reliable transaction consistency, evidence that the current primary cannot meet operational needs, or a tested architecture that guarantees stock decisions are based on current authoritative data.

## What this survives

This decision survives increased order volumes because it protects the correctness of stock decisions even while reporting workloads move elsewhere. It also survives a future warehouse or lakehouse implementation: analytical platforms may improve stock analysis, but they should not become the live transaction authority unless a separate inventory architecture is designed and proven to maintain the required consistency.
