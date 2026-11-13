# Recommendation

# Kloud Kart Data Strategy Engagement

## 1. Executive recommendation

Kloud Kart should adopt a phased data strategy that separates reporting from the live e-commerce application, improves reporting consistency and strengthens customer data management.

Rather than investing in a complex data platform immediately, the company should first address its key challenges: slow website performance, inconsistent revenue figures and inadequate control over customer information.

I recommend that Kloud Kart:

- Set up a MySQL read replica on the pre-approved second server to handle reporting workloads.
- Keep live stock transactions on the primary database while allowing other reports to refresh daily.
- Use SQL and Python for data preparation and validation, with Power BI for dashboards and reporting.
- Establish shared business definitions and data-quality checks.
- Recruit a Data Engineer and an Analytics Engineer/Analyst within the two-hire limit.
- Strengthen customer data controls, including access, retention, deletion and export tracking.

This phased approach addresses immediate business risks while building a practical foundation for future growth.

## 2. Recommended technical approach

### Separate reporting from the live website

Kloud Kart should retain its existing MySQL database as the primary operational database and configure a read replica on the second server for reporting. This will move reporting workloads away from the live website, reducing performance pressure while providing a safer reporting environment. Replication delays should be monitored, and the replica should not replace backups or disaster recovery arrangements.

### Establish appropriate data refresh rates

### Daily refreshes should be sufficient for revenue, orders, customer and operational reports. However, live stock checks and stock-changing transactions must remain on the primary database to ensure accurate stock availability and order fulfilment

### Use SQL, Python and Power BI

SQL should handle data extraction, filtering and aggregation, while Python supports data preparation and validation. Power BI should present approved business measures through dashboards and reports, using imported data with daily refreshes rather than querying the live database continuously.

Finance and Operations must first agree on shared definitions for revenue and orders. Before using Power BI Service, Kloud Kart should also assess licensing costs, access permissions and the implications of transferring data to an external cloud provider. Customer information should be excluded from dashboards unless necessary and properly controlled.

## 3. People and responsibilities

### First hire: Data Engineer

The Data Engineer should take responsibility for the read replica, data extraction, scheduled pipelines, monitoring, backup coordination, access controls and technical documentation. This role protects the reliability of the data foundation and reduces dependence on the existing PHP/MySQL developer for data operations.

### Second hire: Analytics Engineer/Analyst

The Analytics Engineer/Analyst should work with Finance and Operations to define business measures, reconcile reporting differences, validate datasets and develop Power BI dashboards. This role should also help ensure that reports are understandable and useful to business decision-makers.

The existing developer should continue to focus on the e-commerce application and work with the Data Engineer when changes to the operational database are necessary.

## 4. Governance, security and compliance

Kloud Kart should establish clear ownership and controls over customer and business data. Access should be restricted to authorised staff, customer exports should be tracked, and the storage and sharing of customer information should be documented.

The company should review its data practices against Ghana's Data Protection Act, 2012 (Act 843), covering data collection purposes, access, retention, deletion and third-party sharing. The planned Nigeria expansion should also involve a review of applicable data protection requirements.

The DPC complaint should be treated as an immediate priority. Kloud Kart must be able to locate affected customer records and their copies, track deletion actions and provide evidence of how the complaint was handled. The 90-day response period is a case-specific constraint.

## 5. Cost and investment priorities

The board should prioritise investment in five areas:

- **People:** Recruitment and onboarding of the Data Engineer and Analytics Engineer/Analyst.
- **Infrastructure:** Second server, read replica, storage, monitoring and backups.
- **Reporting:** Power BI licences, gateway requirements and supporting tools.
- **Governance:** Data mapping, access reviews, retention, deletion and compliance procedures.
- **Training:** Preparing staff to use and maintain the new reporting processes.

Exact costs should be confirmed through salary estimates, infrastructure quotations and Power BI licensing checks before budget approval. A larger data warehouse or lakehouse should be postponed until reporting needs, data growth and operating costs justify the investment.

## 6. Expected business outcomes

The recommended strategy should deliver the following outcomes:

- Reporting workloads no longer interfere with live website performance.
- Finance and Operations use consistent, documented business figures.
- Daily reports reduce manual CSV processing and improve reporting efficiency.
- Live stock transactions remain accurate through the primary operational database.
- Customer information, access, exports and deletion requests are better controlled.
- Two dedicated data professionals support reliable reporting and data operations.
- Future investment in advanced analytics or larger data infrastructure is guided by measurable business needs.

**Final position:** Kloud Kart should prioritise a reliable and well-governed data foundation before investing in advanced analytics. This will protect current operations, improve management reporting and provide a sustainable foundation for future growth.