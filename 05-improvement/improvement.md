# Customer Data Deletion Tracking Process

**1\. Improvement overview**

**Improvement name:** Customer Data Deletion Tracking Process

**Business area:** Customer Data Governance and Compliance

**Problem owner:** Head of Operations

**Proposed solution:** Introduce a central process for recording, assigning, monitoring and verifying customer data deletion requests.

**2\. Problem being addressed**

Kloud Kart collects and processes customer information through its e-commerce operations. However, the company exports customer lists for marketing activities without properly tracking how many copies exist or where those copies are stored.

This creates a challenge when a customer requests the deletion of their personal information. The company may struggle to identify every location where the information is held, determine who is responsible for handling the request and confirm whether the required action has been completed.

This creates unnecessary compliance risks and makes it difficult for management to demonstrate that customer information is being handled responsibly.

**3\. Proposed improvement**

Introduce a Customer Data Deletion Tracking Process that provides one central record for managing customer deletion requests.

Every request will be recorded, assigned to a responsible employee and monitored until the appropriate action has been completed. The process will also document the locations checked, actions taken, completion dates and supporting evidence.

Requests that cannot be completed immediately will remain visible as outstanding, with the reason for the delay and the next required action recorded.

**4\. Tools and resources required**

The improvement will use familiar Microsoft tools to avoid introducing an unnecessarily expensive system.

| **Tool**                 | **Purpose**                                                                                                    |
| ------------------------ | -------------------------------------------------------------------------------------------------------------- |
| Microsoft Forms          | Provide a standard method for recording incoming deletion requests.                                            |
| Microsoft Excel          | Maintain the central request tracker, including request status, assigned employee and completion evidence.     |
| Microsoft SharePoint     | Store the tracker and supporting records in a controlled location with restricted access.                      |
| Microsoft Power Automate | Send notifications and reminders when requests are received, assigned or approaching their internal deadlines. |

The initial process can operate with Forms, Excel and SharePoint. Power Automate can be introduced to reduce manual follow-up once the process is established.

**5\. How the improvement will work**

The process will follow five stages:

**Stage 1: Receive and record**

When a deletion request is received, an employee records it using Microsoft Forms. The request is assigned a unique reference and its date of receipt is documented.

**Stage 2: Identify customer information**

The responsible employee identifies the systems and locations where the customer's information may be stored. These may include the main MySQL database, marketing exports, spreadsheets and other known copies.

**Stage 3: Assign responsibility**

An employee is assigned to coordinate the request and follow up with the relevant departments or system owners.

**Stage 4: Take the appropriate action**

The relevant employees carry out the required action in the identified locations. Any information that must be retained for a lawful reason is documented rather than automatically deleted.

**Stage 5: Verify and close**

The responsible employee records the action taken, completion date and supporting evidence. The request is marked as completed only after the required checks have been carried out.

**6\. Value to Nana and Kloud Kart**

The improvement provides Nana with a clearer way to monitor how customer deletion requests are handled.

Instead of depending on informal updates from different employees, she can refer to one central tracker to identify outstanding requests, see who is responsible and check whether evidence of completion has been recorded.

For Kloud Kart, the process will:

- Improve accountability for customer information.
- Reduce the risk of customer data being retained unnecessarily.
- Make deletion requests easier to monitor and investigate.
- Improve the company's ability to demonstrate responsible data handling.
- Support compliance with Ghana's Data Protection Act, 2012 (Act 843).

**7\. How success will be measured**

The improvement will be considered successful when:

- Every received deletion request is recorded.
- Every request has an assigned responsible employee.
- Relevant data locations are identified and checked.
- Completed requests have documented actions and supporting evidence.
- Outstanding requests are visible, with reasons for delays and next steps recorded.
- Nana can review the status of requests without having to contact multiple employees for updates.

**8\. Implementation considerations and limitations**

The process should begin with the identification of existing customer data locations and the assignment of responsibility for handling deletion requests.

Access to the tracker and supporting records should be restricted to authorised employees because they may contain personal information.

The proposed tools provide a way to coordinate and monitor deletion requests, but they do not automatically remove customer information from databases, exported files or backups. The relevant employees must carry out and verify the required actions.

The company must also consider applicable legal retention requirements before deleting information. A deletion request should be assessed appropriately rather than treated as an instruction to remove every record regardless of legal obligations.

**9\. Conclusion**

The Customer Data Deletion Tracking Process is a practical improvement that addresses an existing weakness in Kloud Kart's management of customer information. By using familiar tools to establish a consistent process, the company can improve accountability, give Nana better visibility of outstanding requests and strengthen its approach to customer data governance without introducing an expensive technology platform.