# ADR-001: Use a MySQL read replica for business reporting

- Status: Proposed — pending approval
- Date: 2026-11-12
- Decision owner: Kloud Kart leadership, with technical input from the PHP/MySQL developer and proposed Data Engineer

## Context

Kloud Kart's orders, inventory and customer accounts are held in a MySQL database that shares a server with the live website. Monday reporting exports involve large volumes of data, and reporting activity has slowed the live website twice in the last month. The company has approval to use a second server or read replica, but it must protect the availability of the live shop.

The immediate problem is not that MySQL is necessarily unsuitable. The problem is that operational website activity and analytical reporting compete for the same resources.

## Decision

Keep the existing MySQL database as the operational source of truth and configure a MySQL read replica on the approved second server. Run routine reporting extracts and analytical queries against the replica rather than the live primary database.

The replica must be monitored for replication delay and tested before it becomes the normal reporting source. It does not replace backups or a disaster-recovery arrangement.

## Alternatives considered

### Alternative A: Continue running reports against the production database

- How it would work: Keep the current arrangement and schedule or optimise reporting queries on the same MySQL server used by the live website.
- Why it is attractive: It requires the least infrastructure change and avoids the setup and maintenance of a second server.
- Why rejected: The current arrangement has already slowed the live website. Query optimisation alone does not remove competition for the same server resources, so it leaves a known operational risk in place.

### Alternative B: Build a full data warehouse immediately

- How it would work: Introduce a separate analytical platform and build pipelines to move data from MySQL into it.
- Why it is attractive: It could provide a more scalable analytical environment and a foundation for more advanced reporting.
- Why rejected: Kloud Kart has a small technical team, a two-hire limit and an immediate performance problem. A full warehouse would add cost and implementation work before the company has established stable reporting requirements and data definitions.

## Consequences

- What this buys: Reporting workloads are separated from the live website database; the company can use its approved second server; and the existing MySQL application does not need to be replaced as the first step.
- What this costs: Additional hosting and storage, replica configuration, monitoring, testing and ongoing operational responsibility.
- What it costs the client if I am wrong: If replication is unreliable or the replica is poorly monitored, reports may be delayed or incomplete. If the replica is not sufficient to reduce production load, Kloud Kart may need further query optimisation or a different analytical architecture.
- What would make me revisit this: Persistent replication failures, unacceptable replication lag, continued website slowdowns caused by reporting, or evidence that reporting volumes and complexity require a dedicated warehouse.

## What this survives

This decision remains useful even if Kloud Kart's order volumes grow by the expected 15–20% per year: it separates routine reporting from live transactions without requiring an immediate platform replacement. It also survives a later move to a warehouse, because the replica can serve as an interim reporting source or controlled extraction point while the longer-term architecture is evaluated. It does not depend on the assumption that the replica is a backup or that replication is instantaneous.
