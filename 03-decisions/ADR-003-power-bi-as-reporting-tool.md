# ADR-003: Adopt Power BI as the initial reporting and dashboard tool

- Status: Proposed — pending approval
- Date: 2026-11-12
- Decision owner: Kloud Kart leadership, with input from Finance, Operations and the proposed Analytics Engineer/Analyst

## Context

Kloud Kart needs consistent reports that Finance and Operations can use without repeatedly rebuilding figures from CSV exports. The company needs a reporting tool, but the underlying reporting data and metric definitions must first be prepared and validated.

The strategy selects Power BI for dashboards and business reporting. It is important to distinguish the reporting tool from the data platform: Power BI does not replace MySQL, create reliable data definitions by itself, or resolve source-data quality problems.

## Decision

Use Microsoft Power BI as the initial business reporting and dashboard tool. Start with imported reporting data and a daily refresh, sourced from the reporting environment rather than continuous queries against the live application database.

Before using Power BI Service, confirm licensing, gateway requirements, access controls and the implications of transferring reporting data to an external cloud service. Exclude personal customer information from reports unless it is necessary and appropriately protected.

## Alternatives considered

### Alternative A: Use Metabase

- How it would work: Deploy Metabase as the business intelligence interface and connect it to the reporting database or replica.
- Why it is attractive: It is a recognised alternative for database-connected dashboards and may offer a simpler or lower-cost starting point depending on hosting and deployment choices.
- Why rejected: Kloud Kart has selected Power BI as its preferred reporting tool for this engagement. Introducing a different tool would depart from that direction and require a separate evaluation of user experience, administration, support and total cost. Metabase should remain a valid option if Power BI licensing or deployment requirements prove unsuitable.

### Alternative B: Use Tableau or another enterprise BI platform

- How it would work: Adopt another commercial BI platform for dashboards, reporting and governed analytics.
- Why it is attractive: These platforms can support sophisticated visual analytics and enterprise reporting requirements.
- Why rejected: Kloud Kart has not demonstrated requirements that justify evaluating or paying for a more complex alternative at this stage. The immediate priority is to establish trusted measures and reliable daily reporting, not to maximise visualisation features.

### Alternative C: Continue using spreadsheets as the main reporting interface

- How it would work: Continue exporting CSV files and manually preparing reports in spreadsheets.
- Why it is attractive: Staff already use this approach and it requires no new BI platform.
- Why rejected: The current process is time-consuming and contributes to inconsistent figures between Operations and Finance. It does not provide a sufficiently controlled or repeatable reporting process.

## Consequences

- What this buys: A consistent reporting interface for agreed business measures and dashboards that can support management review.
- What this costs: Power BI licences may be required; the company must assess gateway setup, administration, training and cloud-service implications. The actual licence and deployment cost must be confirmed before purchase.
- What it costs the client if I am wrong: If licensing, user access or cloud-data requirements do not fit Kloud Kart's circumstances, the company may incur avoidable costs or need to migrate reports to another tool. If metric definitions are not agreed first, dashboards may make conflicting figures look more authoritative without making them correct.
- What would make me revisit this: Confirmed licensing or gateway costs that exceed the approved budget, security or data-transfer requirements that cannot be met, poor user adoption, or a material change in reporting needs.

## What this survives

This decision survives the current need for daily rather than real-time reporting because Power BI can present scheduled reporting outputs without requiring continuous queries against the production database. It also survives future platform changes: Power BI can remain the presentation layer while the underlying reporting store evolves. The decision is conditional on a privacy, security, licensing and gateway review; it is not approval to transfer all customer data to the cloud.
