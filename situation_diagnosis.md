Situation Diagnosis

# 1. Executive assessment

Kloud Kart has outgrown its informal approach to data management. Although the company processes approximately 4,000 orders daily, its current data environment creates challenges with website performance, reporting reliability, customer data management and its ability to support future growth.

The central problem is not the absence of an advanced data warehouse or real-time analytics platform. It is the lack of a controlled, reliable and sustainable process for managing, processing and reporting business data. The production MySQL database supports both customer transactions and large reporting activities; Operations and Finance independently prepare reports that do not agree; and Marketing maintains approximately 300,000 customer records without tracking how many copies of its customer lists exist.

These weaknesses create operational, financial and regulatory risks. Kloud Kart should address them before investing in more advanced data technologies.

# 2. Root-cause analysis and business costs

## 1. Reporting workloads compete with the live website

**Priority:** Critical

**Root cause:** The production MySQL database handles customer transactions and analytical reporting on the same server. Large reporting queries therefore compete with live customer activity for database and server resources. This is consistent with the two website slowdowns reported during the previous month.

**Potential business cost:** Potential costs include lost sales from abandoned purchases, delayed transactions, developer troubleshooting time and damage to customer confidence.

**Evidence needed:** Measure incident duration and frequency, affected sessions and orders, database CPU/memory/disk use, and the queries responsible for the reporting workload.

## 2. Customer information lacks effective governance

**Priority:** Critical

**Root cause:** Kloud Kart does not sufficiently control how customer information is accessed, exported, stored, shared, retained and deleted. Customer-list exports can create copies outside the original database without the company's knowledge. Deleting a record from MySQL does not automatically remove copies in spreadsheets, backups or third-party systems.

**Potential business cost:** Potential costs include investigation and administrative expenses, legal and compliance advice, regulatory consequences and reputational damage.

**Evidence needed:** Identify data-copy locations, employees and third parties with access, retention and deletion procedures, deletion evidence, and Data Protection Commission registration/compliance status.

## 3. Business reporting lacks consistent definitions and controls

**Priority:** High

**Root cause:** The company has no established process for defining, calculating and validating important business measurements. For example, Operations may calculate revenue using all orders placed, while Finance may include only paid or completed orders. Different periods, duplicate orders, cancellations, refunds, discounts and manual spreadsheet errors are other possible causes; these have not been confirmed from the actual reports.

**Potential business cost:** Potential costs include staff time spent reconciling spreadsheets, delayed decisions, unreliable financial reporting and reduced investor confidence.

**Evidence needed:** Compare both departments' calculation methods, reporting periods and source data; measure the number/value of differing records and time spent preparing and reconciling reports.

## 4. Kloud Kart lacks dedicated data management capability

**Priority:** High

**Root cause:** The company has one PHP/MySQL developer but no one with professional experience managing a data warehouse or developing Python data pipelines. Reporting and data management therefore depend heavily on manual work and individual knowledge.

**Potential business cost:** Potential costs include recruitment and training, implementation delays, developer bottlenecks and higher maintenance costs for systems the team cannot support.

**Evidence needed:** Assess developer workload, reporting effort, skills needed to operate the proposed environment, salary expectations and current backup/monitoring responsibilities.

## 5. Technology ambitions are ahead of business requirements

**Priority:** Medium

**Root cause:** The company is considering a warehouse or lakehouse, real-time dashboards and machine learning without first establishing the business requirements and operating capability. The brief says stock counts cannot go stale, while other reporting can refresh daily; this does not establish a need for real-time management reporting.

**Potential business cost:** Potential costs include unnecessary licensing and infrastructure, training and maintenance, implementation complexity and delayed resolution of immediate problems.

**Evidence needed:** Identify decisions that genuinely need real-time information, departmental refresh needs, supplier costs, maintenance requirements and measurable value from forecasting.

# 3. Risk ranking and prioritization

| **Rank** | **Root cause**                                       | **Likelihood**                           | **Business impact** | **Priority** |
| -------- | ---------------------------------------------------- | ---------------------------------------- | ------------------- | ------------ |
| 1        | Reporting workload competing with the live website   | High — incidents already occurred        | Critical            | Critical     |
| 2        | Weak customer data governance                        | High — uncontrolled copies are confirmed | Critical            | Critical     |
| 3        | Inconsistent business reporting                      | High — differences are ongoing           | High                | High         |
| 4        | Lack of dedicated data management capability         | High — skills gap is established         | High                | High         |
| 5        | Technology investment ahead of business requirements | Medium                                   | Medium              | Medium       |

Production database performance ranks first because it has already affected the live website and can interfere directly with customer transactions. Customer data governance ranks second because uncontrolled copies create compliance and reputational exposure, made more urgent by the outstanding complaint. Reporting reliability ranks third because management and investors need trustworthy figures. The capability gap ranks fourth because improvements must be maintainable. Technology investment ranks fifth because it is a longer-term investment risk, while the other issues require more immediate attention.

# 4. Cost assessment

| **Root cause**                  | **Potential cost to Kloud Kart**                                                     | **Information needed to quantify**                                                 |
| ------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Website performance             | Lost sales, abandoned purchases, delayed transactions and developer troubleshooting. | Affected orders, average order value, incident duration and troubleshooting hours. |
| Customer data governance        | Investigation, legal, regulatory and reputational costs.                             | Number of copies, access records, third-party sharing and deletion workload.       |
| Inconsistent reporting          | Staff time, delayed decisions and unreliable financial reporting.                    | Reconciliation hours, staff costs and value of affected decisions.                 |
| Skills gap                      | Recruitment, training, implementation and maintenance expenses.                      | Salary expectations, training requirements and technical workload.                 |
| Premature technology investment | Unnecessary licensing, infrastructure, training and maintenance.                     | Supplier quotations, infrastructure requirements and total ownership costs.        |

The case study does not provide financial statements, hosting invoices, salary estimates or incident records. Exact monetary losses therefore cannot be calculated reliably. The costs above are potential business exposures, not confirmed financial losses. Actual operational records, financial information and supplier quotations are required to quantify them.

# 5. Compliance and customer data risks

Customer information management requires particular attention because the brief identifies Ghana's Data Protection Act, 2012 (Act 843). The lack of visibility over exported customer-list copies raises concerns about access, retention, deletion, third-party sharing and accountability.

| **Area**            | **Current concern**                                           | **Required control**                            |
| ------------------- | ------------------------------------------------------------- | ----------------------------------------------- |
| Data access         | Customer-list copies are not tracked.                         | Authorized and controlled access.               |
| Data retention      | Unclear how long copies are kept.                             | Defined retention periods.                      |
| Data deletion       | No established tracking of all copies.                        | Documented deletion process.                    |
| Third-party sharing | Customer exports may circulate without sufficient visibility. | Controlled sharing and appropriate safeguards.  |
| Accountability      | Customer data ownership and responsibilities are unclear.     | Assigned responsibility and processing records. |

Kloud Kart should identify where the affected customer's information exists, determine which copies need to be addressed, document the actions taken and retain evidence of its response. It should also verify its Data Protection Commission registration and applicable obligations under Act 843. The Nigeria pilot should be assessed for relevant cross-border data protection requirements.

The 90-day response requirement is treated as a constraint supplied by the case study, not as a general statutory deadline under Act 843.

# 6. Discovery questions

| **Area**              | **Questions to validate the diagnosis**                                                                           |
| --------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Reporting             | How do Operations and Finance calculate revenue? Which figure is used for management decisions?                   |
| Database performance  | Which exports cause slowdowns? How long do they run, and when do they occur?                                      |
| Customer information  | Where are customer lists stored, who can access them, and how are copies deleted?                                 |
| Compliance            | Is Kloud Kart registered with the Data Protection Commission? What evidence exists for the outstanding complaint? |
| Technical capability  | How much time does the developer spend supporting reporting and database maintenance?                             |
| Business requirements | Which activities genuinely require real-time information beyond live stock availability?                          |
| Financial planning    | What are current infrastructure costs, and what budget is available for salaries and software?                    |
| Nigeria expansion     | What customer information will be processed in Nigeria, and where will it be stored?                              |

Nana is unavailable for follow-up, so these questions remain documented validation requirements. The recommendation must proceed using the facts in the brief and clearly identified assumptions.

# 7. Assumptions and limitations

## Facts provided by the case study

- Kloud Kart is a three-year-old e-commerce company operating in Accra and has started piloting in Nigeria.
- It ships approximately 4,000 orders daily and has a MySQL database of approximately 40 GB.
- The database and website share one server; reporting exports slowed the website twice in the previous month.
- Marketing maintains approximately 300,000 customer records.
- The company has one PHP/MySQL developer and budget for two data hires.
- A second server or read replica is pre-approved.
- Stock counts cannot go stale, while other reporting can refresh daily.

## Assumptions requiring validation

- MySQL is the primary source of truth for orders, inventory and customer accounts.
- Reporting exports are executed against the production database.
- The company has no formally agreed definitions for important business measurements.
- Customer exports are not centrally tracked.
- Daily refreshes are sufficient for management reporting.
- The existing application can continue handling authoritative stock transactions independently of reporting.

## Information unavailable

- Actual database schema and table sizes.
- Current infrastructure and hosting costs.
- Website performance measurements and database monitoring records.
- Order values, profit margins and conversion rates.
- Existing backup and disaster recovery arrangements.
- Data Protection Commission registration and compliance status.
- Customer consent and retention practices.
- Exact contents of Finance and Operations spreadsheets and the actual reasons their figures differ.

This diagnosis is based on the supplied case study rather than a direct audit of Kloud Kart's production systems. Assumptions are used to guide the assessment and should not be presented as confirmed findings.

# 8. Final consultant's position

Kloud Kart's main challenge is not the absence of advanced data technology. It is the absence of a reliable and controlled data management foundation. The company is exposing its live website to reporting workloads, cannot confidently reconcile its business figures and lacks sufficient control over customer information. These weaknesses are made more serious by its limited technical capacity, funding expectations and planned expansion into Nigeria.

- Protect the live website from reporting-related performance problems.
- Establish control over customer information and address the outstanding complaint.
- Agree on business measurement definitions and establish reliable reporting.
- Build the technical capability needed to maintain improvements.
- Introduce advanced analytics only when a measurable business requirement justifies the investment.

**Conclusion:** Kloud Kart should prioritize operational stability, trusted business reporting and responsible customer data management before investing in real-time analytics or machine learning. Establishing these foundations will help the company make better decisions, protect customer information and support future growth without introducing unnecessary technology or operational complexity.**