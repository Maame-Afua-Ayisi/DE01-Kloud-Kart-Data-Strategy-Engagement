# ADR-005: Hire a Data Engineer before an Analytics Engineer/Analyst

- Status: Proposed — pending approval
- Date: 2026-11-12
- Decision owner: Kloud Kart leadership, within the approved two-hire budget

## Context

Kloud Kart has one PHP/MySQL developer and no established data engineering or professional Python capability. The current reporting process relies on large manual exports, has affected live website performance, and produces inconsistent figures between Finance and Operations.

The board has approved two data hires, not three. The company therefore needs to sequence the roles so that the technical foundation is reliable before expanding reporting and analysis.

## Decision

Recruit a Data Engineer first to establish and operate the reporting data foundation, including the read replica, scheduled data movement, monitoring, access controls and documentation. Recruit an Analytics Engineer/Analyst next to define business measures, validate reporting data, reconcile figures with Finance and Operations, and build Power BI dashboards.

Both roles are part of the two-hire plan; the sequence reflects the immediate operational risk.

## Alternatives considered

### Alternative A: Hire the Analytics Engineer/Analyst first

- How it would work: Recruit the person responsible for business measures and dashboards before recruiting the person responsible for data infrastructure and pipelines.
- Why it is attractive: It could deliver visible dashboards and address the disagreement between Finance and Operations earlier.
- Why rejected: The underlying reporting process is still dependent on large exports from a database that shares resources with the live website. Building dashboards before establishing a safe and reliable data source risks automating an unstable process and leaving the main operational risk unresolved.

### Alternative B: Hire one senior generalist to cover both roles

- How it would work: Recruit one person expected to manage infrastructure, data pipelines, metric definitions, reporting, governance and stakeholder support.
- Why it is attractive: It appears to reduce recruitment and salary costs and fits within the headcount limit.
- Why rejected: The scope combines distinct engineering and analytical responsibilities. With the current workload and limited in-house data capability, relying on one person creates a concentration risk and may delay either the technical foundation or the reporting improvements.

### Alternative C: Hire a third data specialist

- How it would work: Recruit separate data engineering, analytics and governance specialists.
- Why it is attractive: It would provide more dedicated capacity across the work.
- Why rejected: The case explicitly limits the company to two data hires this financial year. The strategy must operate within that constraint.

## Consequences

- What this buys: The first hire addresses the immediate reliability and separation problem; the second can then build trusted business reporting on a more stable foundation. Responsibilities are clearer than assigning every task to one generalist.
- What this costs: Recruitment and salaries for two roles, onboarding time, and the need for coordination with the existing PHP/MySQL developer and business teams.
- What it costs the client if I am wrong: If the Data Engineer is difficult to recruit or the replica work takes longer than expected, dashboard delivery may be delayed. If the Analytics Engineer/Analyst role is not clearly scoped, metric ownership and user adoption may remain weak.
- What would make me revisit this: A change to the two-hire limit, evidence that an available candidate can credibly cover both skill sets, or a change in the immediate priorities that makes analytical reconciliation more urgent than infrastructure separation.

## What this survives

This sequence survives pressure to show quick dashboard progress because it prioritises removing a known risk to the live website and creating a dependable source for reporting. It also survives the two-hire constraint: both essential capabilities are covered without assuming a third role. If recruitment timing changes, Kloud Kart can use limited external support for a defined task, but should not quietly transfer ongoing ownership of the data foundation to the existing application developer.
