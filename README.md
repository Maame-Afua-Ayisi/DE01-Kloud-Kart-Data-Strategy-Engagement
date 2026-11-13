**Kloud Kart Data Strategy Engagement**

**Project Overview**

This project presents a proposed data strategy for Kloud Kart, a growing e-commerce business based in Accra, Ghana.

The engagement focuses on addressing the company's reporting challenges, improving database performance, strengthening customer data management and establishing a scalable foundation for future business analytics.

The recommendations are designed to support Kloud Kart's current operations while preparing the business for continued growth and expansion into new markets.

**Business Challenge**

Kloud Kart currently operates its e-commerce platform using a MySQL database that handles website transactions, orders, inventory and customer information.

As the business grows, reporting activities involving large data exports are placing additional pressure on the operational database. This creates performance risks for the live website and makes reliable business reporting more difficult.

The company also needs stronger processes for managing customer information and meeting its data protection responsibilities.

**Project Objectives**

The objectives of this engagement are to:

- Identify the root causes of Kloud Kart's data and reporting challenges.
- Recommend a practical data architecture that separates reporting workloads from live transactions.
- Establish consistent and reliable business reporting.
- Improve customer data governance and accountability.
- Develop a phased implementation roadmap.
- Document key architectural and strategic decisions.
- Propose an additional improvement to strengthen customer data deletion tracking.

**Key Recommendations**

The proposed strategy recommends:

- Retaining MySQL as the primary operational database.
- Introducing a MySQL read replica to handle reporting workloads.
- Adopting daily reporting for management and operational insights.
- Using Power BI for business intelligence and dashboard visualisation.
- Keeping live inventory operations on the primary database to protect stock accuracy.
- Hiring a Data Engineer before expanding the analytics function.
- Introducing a customer data deletion tracking process to improve accountability.

**Project Deliverables**

This repository contains five main deliverables:

1. **Situation Diagnosis:** Identifies the underlying business and technical problems, associated risks and areas requiring improvement.
2. **Recommendation and Roadmap:** Presents the proposed data strategy and a phased 12-month implementation plan.
3. **Architecture Decision Records (ADRs):** Documents the key decisions, alternatives considered and expected consequences.
4. **Board Presentation:** Communicates the proposed strategy, decisions, roadmap and expected business outcomes to stakeholders.
5. **Additional Improvement:** Proposes a customer data deletion tracking process to strengthen customer data governance.

**Proposed Technology**

The strategy considers the following technologies and tools:

- **MySQL:** Operational database.
- **MySQL Read Replica:** Reporting workload separation.
- **SQL and Python:** Data extraction, preparation and validation.
- **Power BI:** Business intelligence and reporting.
- **Microsoft Forms, Excel, SharePoint and Power Automate:** Proposed tools for managing customer data deletion requests.

These are proposed technology choices and do not imply that the systems have already been implemented.

**Implementation Approach**

The proposed strategy follows a phased approach over 12 months:

- Establish the reporting infrastructure and improve data access.
- Automate reporting and introduce management dashboards.
- Strengthen data quality and customer data governance.
- Evaluate future analytics opportunities as the business becomes more data-ready.

The approach prioritises business continuity, practical implementation and measurable business outcomes.

**Implementation Status**

This repository contains the strategic recommendations, documentation, decision records, roadmap and presentation developed for the engagement.

It represents a proposed data strategy rather than a completed technical implementation. Infrastructure configuration, automated pipelines, dashboards and reporting workflows would be delivered during the implementation phases.

**Expected Outcomes**

The proposed strategy aims to deliver:

- Improved website performance by reducing reporting pressure on the operational database.
- More consistent and reliable business reporting.
- Better visibility into business performance.
- Improved inventory accuracy.
- Stronger customer data governance.
- A scalable foundation for future analytics and business expansion.

**Compliance Considerations**

The proposed approach recognises the importance of protecting customer information and complying with applicable data protection requirements, including Ghana's Data Protection Act, 2012 (Act 843).

Customer data access, retention, deletion and processing practices should be reviewed and managed throughout implementation.

**Project:** DE01 Kloud Kart Data Strategy Engagement  
**Organisation:** Kloud Kart  
**Status:** Proposed Data Strategy