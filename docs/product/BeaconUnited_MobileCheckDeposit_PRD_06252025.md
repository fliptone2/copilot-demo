# **API PRD: Mobile Check Deposit | Beacon United | D1 Flex**  {#api-prd:-mobile-check-deposit-|-beacon-united-|-d1-flex}

**Updated**: 6/25/2025  
**Status**: Draft | **In Review** | Approved

| Authors | Jen Childress |
| :---- | :---- |
| Collaborators/Reviewers | Sara Betsey, Charita Archana, Mac Glore, Numan Hammoudeh, Olga Ermolova, Lavanya Jayaram, Michael Daugherty (Concentrix), Paul Nowling (Concentrix) |
| Approvers | Karl Asha, Parijat Sinha, Rob Lamoureux |

**Contents**

**[API PRD: Mobile Check Deposit | Beacon United | D1 Flex	1](#api-prd:-mobile-check-deposit-|-beacon-united-|-d1-flex)**

[*Problem Statement / Introduction	1*](#problem-statement-/-introduction)

[*In Scope	2*](#in-scope)

[*Out of Scope	2*](#out-of-scope)

[*Business Justification	2*](#business-justification)

[*Functional Requirements (Use Cases)	3*](#functional-requirements-\(use-cases\))

[*Non-Functional Requirements	5*](#non-functional-requirements)

[*Compliance	7*](#compliance)

[*Hypothesis of Success and Metrics	7*](#hypothesis-of-success-and-metrics)  
[Assumptions	7](#assumptions)  
[Metrics	7](#metrics)

[*Dependencies	8*](#dependencies)

[*Schedule and Milestones \= TBD	9*](#schedule-and-milestones-=-tbd)

[*Risks	9*](#risks)  
[Business Risks	9](#business-risks)  
[Security/Compliance Risks	9](#security/compliance-risks)

[*Appendix	10*](#appendix)  
[Change Log	10](#change-log)  
[Glossary	10](#glossary)  
[Important Links	10](#important-links)  
[Open Questions	10](#open-questions)

## **Problem Statement / Introduction** {#problem-statement-/-introduction}

Today, FIS makes API discovery a barrier. The process to reach a simple "hello, world" takes too long. Even when developers find the correct APIs, they encounter ongoing friction. There is a lack of clear guidance on use cases, the sequence for calling multiple endpoints, and how to combine endpoints into specific use cases or useful recipes. This results in frustration and necessitates intervention from FIS' professional services teams and statements of work, for tasks that should be straightforward and self-service.

FIS' clients/developers also struggle to access a unified set of APIs/SDKs/widgets for integration with FIS products and digital channels. Instead, developers interact with multiple sets of product-specific APIs that lack consistent design as well as find numerous system APIs that are not orchestrated for ease of use.

To remain competitive, FIS must offer a modern mobile check deposit solution that provides a unified API interface to support the capture, validation, and submission of check images through mobile devices. We must abstract the complexity of serving multiple remote deposit capture backend systems (FIS and non-FIS products) so that we offer a consistent experience for developers as well as end users.

## **In Scope** {#in-scope}

Consistent with the Beacon United tenets for reusability and unification across all digital channels, FIS should provide a consistent, intuitive, and modular set of APIs for any Digital One product to leverage when adopting new digital banking functionalities. As a result, an Open Banking API will be needed for offering mobile check deposit for digital banking use cases. Overall, scope includes:

* Support of mobile check deposit for retail banking consumers and small businesses, which are the current target customer base for D1 Flex Mobile  
* Integration to IBS and HORIZON banking cores via the Open Banking layer and its APIs  
* An orchestrated, open banking **(to be named)** process API(s) will need to be developed for mobile check deposit

The orchestrated open banking process API(s) must enable the following experiences:

* Enable our banking clients to offer mobile check deposit to their customers  
  * Support image capture and submission  
  * Validate deposit eligibility per account and user and enforce daily deposit limits (per item and per user)  
  * Offer check deposit status lookup (accepted, rejected, pending review)  
* Abstract integration differences across multiple remote deposit capture providers, FIS and non-FIS  
* Provide routing logic based on the bank’s underlying mobile check deposit product for image capture as well as the core banking system for transaction posting  
* Maintain a traceable transaction ID across the orchestrated process, logging all steps, and retaining logs for compliance  
* Return normalized error codes and descriptions that are user-friendly

## **Out of Scope** {#out-of-scope}

* In P0, integration to DirectLink Consumer (DLC) – will be a fast follower post Q3 2025 release.  
* Non-English language support  
* Integration to other FIS core banking systems such as Bancpac, Bankway, or AffinityEdge (FKA Miser)  
* Support for D1B or D1 Studio  
* Support for DirectLink Merchant check deposit for businesses/organizations

## **Business Justification** {#business-justification}

The capability of an end user depositing a check is critical for any mobile banking app and ranks in the top (3) valued features for mobile. FIS will not be able to deliver the new Beacon United Mobile app to the market without mobile RDC.

## **Functional Requirements (Use Cases)** {#functional-requirements-(use-cases)}

| \# | Feature | Priority | Use Case and Justification |
| ----- | :---- | :---: | ----- |
| R-1 | Image Capture and Submission | P0 | As Edwin End User I want to be able to take a picture of checks that I receive so that I can deposit them digitally into my bank account. I want to log in securely to my mobile app so that I can access mobile check deposit. I want to be able to select which of my accounts will receive the check deposit so that I can put the money in the correct place. I want to enter the amount of the check so I can confirm the amount of money being deposited is correct. I want to easily take photos of the front and back of the check to be deposited so that I can submit the images for deposit. I want to be given feedback on the images captured so that I can easily correct problems/issues before I submit the check images for deposit. I want to review all the check deposit details and images are correct before I choose to submit them so I ensure everything is correct. I want to view a list of my past mobile check deposits so that I can track them and their status. I want to see that my account balance changes as a result of the check deposit and that the transaction appears in my transaction history so that I know my transaction was successful. I also want to be able to see the check images associated with my check deposit in my account’s transaction history so that I can confirm from whom and on what date that I received the check. *As Bank employees* We want to offer our customers with the ability to make mobile check deposits using a secure method so that we keep our customers’ personal banking information safe. As Sam Support Representative, I want to be able to search for my customer’s mobile check deposit by date, name, or check number so that I can assist him/her/them with any issues being experienced. As Carol Compliance Officer, I want to generate a report of all mobile check deposit activity within a date range so that I can meet audit and regulatory requirements. *As Daphne Developer* I want to use an integration tool (API(s), no/low code, widgets) that offers me the ability to enable end users to deposit checks using my digital banking app so that I can integrate that capability easily, in real time. I want to access up-to-date API documentation and sandbox credentials so that I can start integrating mobile check deposit into my app. I want to initiate a new check deposit session using a single API call so that I can associate the session with a specific check and user. I want to upload the front and back of check images in supported formats such as JPG or TIFF so that the API can validate and process the images. I want to retrieve a customer’s mobile check deposit history so that I can show the most recent deposits and their statuses in my app. I want to use a check deposit API that support secure authentication so that my integration and my customers’ data remains secure and compliant. I want the API to encrypt all personally identifiable information (PII) so that it is secure at rest and in transit. |
| R-2 | Eligibility and Limits | P0 | As Bank employees As Frank Fraud Analyst, I want to be alerted when a mobile check deposit is duplicated incorrectly or exceeds limits that my bank sets for users and accounts so that I can take action before the funds are released. As Owen Operations Manager, I want to view dashboard metrics on mobile check deposits (volume, errors, latency) so that I can monitor performance and service level compliance. As Bob Banking Product Owner, I want to decide/configure which customers or account types are eligible for mobile check deposit so that I can manage risk and ensure proper access for my customers. As Daphne Developer I want the check deposit API to abstract differences between the underlying remote deposit capture products powering the API so that I don’t have to manage differences in specific behavior or data formats. I want to retrieve deposit limits for a specific user and account so that I can prevent users from exceeding their limits before submitting check deposits. |
| R-3 | Status and Notifications | P0 | As Edwin End User I want to receive confirmation that my deposit was submitted so that I know it is being processed/in process. I want to receive real-time updates or notifications when my check deposit is accepted, rejected, or placed on hold so that I can stay informed of the status of my money being deposited. As Bank Employees We want to offer our customers with the ability to easily understand the status of a check deposit so that they can track their money effectively. As Daphne Developer I want to call a validation endpoint with check amount and account information so that I can verify limits, eligibility, and image quality before my app end users submit them. I want to be able to check the status of a submitted deposit using a unique ID so that I can display real-time updates to my app end users such as pending, accepted, or rejected. I want to receive notifications of events when a check deposit status changes so that I can update my app’s user interface without needing to poll the API. |
| R-4 | Error Handling and Retry | P0 | As Edwin End User I want to receive clear messages if my deposit fails or is rejected (such as duplicate deposit, limit being exceeded, or poor image quality) when my deposit is complete so that I am not unclear on the reason for the failure/rejection. As Daphne Developer I want to receive clear and consistent error codes and messages so that I can troubleshoot issues correctly and present helpful messages to my app end users. I want the API to return normalized error and status codes such as LIMIT\_EXCEEDED, BAD\_IMAGE\_QUALITY, or DUPLICATE\_ITEM so that I can clearly understand why a check deposit is being rejected. I want the API to automatically retry failed submissions to the primary remote deposit capture product being used by the customer and powering the API so that my end users don’t have to resubmit check deposits. I want the API to provide user-friendly error messages and retry guidance so that it is easy to use when integrating. |
| R-5 | Integration | P0 | As Daphne Developer I want the API to normalize check deposit submission, status polling, and error handling so that I don’t have to understand nuances between remote deposit capture products powering the check deposit API. I want the API to support remote deposit capture product-specific features such as batch processing or cutoff times so that I can use one API for multiple banking clients that use disparate RDC product solutions. I want the API to offer a sandbox for preproduction integration so that I can test against the API before going live with real customer data. I want the API to offer real life scenarios as test cases which include valid deposit, invalid images, exceeding limits, duplicate deposit, and remote deposit capture (RDC) product service failure so that I can easily test the integration. |
| R-6 | Remote Deposit Capture Abstraction | P0 | As Daphne Developer I do not want to handle remote deposit capture product specific behaviors when I interact with the API so that I have an intuitive and easy integration experience. I want all remote deposit capture product specific logic, status mapping, and formatting to be handled within the orchestration layer so that I don’t have to handle it. |
| R-7 | Documentation and Software Documentation Kits (SDKs) | P0 | As Brad Banker I want to be able to understand the capabilities of the API without the technical jargon so I can properly evaluate if the API will solve for my customers’ needs/problems. As Daphne Developer I want to be able to easily find the Open API specification, any Postman collections, and SDKs (if provided) for the API on FIS Code Connect so that I can understand how to use the API intuitively. |

## **Non-Functional Requirements** {#non-functional-requirements}

The following API/Integration NFRs should be paired closely with the NFRs expected by the consuming application (D1 Flex Mobile) that are found in their PRD, [Deposit Check Beacon United](https://fisglobal.sharepoint.com/:w:/r/teams/PRDCollaborationandReview/Shared%20Documents/General/4.%20Top%2012%20Competitive/PRD%20-%20Deposit%20Check%20Beacon%20United.docx?d=w18f6a582f1ce46c38811707358a24d30&csf=1&web=1&e=DHP4Ws).

| No. | Requirement | Explanation |
| :---- | :---- | :---- |
| NFR-1 | Performance and Scalability | **Response Time:** 	The API must make the check deposit within **2 seconds** **for 95% of transactions** in a normal load situation. **Throughput:**	The API must handle **100 requests per second**, based on expected peak usage. **Scalability:**	The API must scale **horizontally** to support increased demand, leveraging load balancing and auto-scaling. The API must also accommodate a growing number of users and deposits without degradation in performance. **Latency:	Less than** **100 milliseconds** before the API begins processing a request. |
| NFR-2 | Availability and Reliability | **Uptime:**	The API should maintain **99.99% uptime** to ensure uninterrupted access for users needing to deposit checks at any time. **Fault Tolerance:**	Implement **retry mechanisms** and failover strategies to handle service disruptions. **Degradation:**	If an externally dependent system is down (e.g. Funds eXpress or DirectLink Consumer), the API should **gracefully** return cached or partial data rather than failing entirely. **Timeouts:**	Ensure that API calls to downstream services **timeout appropriately** to prevent cascading failures. |
| NFR-3 | Security and Compliance | **Authentication/Auth:**	Strong authentication and authorization to prevent unauthorized access. **Data Encryption:**	Use **TLS 1.2+** for data in transit and **AES-256** for data at rest. **Access Control:**	Implement **role-based access control (RBAC)** to restrict access to check deposit capability. **Data Privacy:**	Ensure compliance with GLBA/NPI, GDPR, and PSD2 laws.Secure transmission and storage of check images and sensitive data (encryption in transit and at rest). **Audit Logging:**	Maintain logs for **security audits**, including request metadata, authentication events, and data access. |
| NFR-4 | Maintainability and Observability | **Maintainability:**                Well-documented code and API endpoints for easy updates and troubleshooting. **Logging/Monitoring:**	Integrate with **X** tools for real-time monitoring. **Error Handling:**	Implement structured error responses using **HTTP status codes and meaningful error messages**. **Tracing:**	Use **distributed tracing** to track request flows across services. **Versioning:**	Support **API versioning** per FIS API Center for Enablement standards to prevent breaking changes. |
| NFR-5 | Interoperability and Compliance | **Standards Compliance:**	Ensure compliance with **FIS API Center for Enablement standards**, compatibility with **RESTful principles,** and industry standards like **FDX/ISO-20022**. **3rd\-Party Integration:**	Allow seamless integration with fintech apps, payment gateways, and aggregators. |
| NFR-6 | Resource Utilization | **Efficient Queries:**	Optimize database queries to minimize load on core banking systems and other systems of record. **Caching Strategy:**	Use **Redis** or similar for caching account data when applicable. |
| NFR-7 | Portability and Compatibility | **Portability:**	Support for multiple mobile platforms and device types. |
| NFR- 8 | Usability | **Usability:**	Intuitive error messages and feedback for common issues (unreadable images, missing check endorsements, etc.)Consistent and user-friendly API responses and documentation. |

## **Compliance** {#compliance}

* *Data Privacy and Security:* Ensure that applicable APIs comply with data protection regulations such as GDPR, CCPA, and other relevant laws. Implement robust encryption methods for data in transit and at rest to protect sensitive information.  
* *Audit Trails and Reporting*: Maintain detailed logs of all transactions and interactions through the API(s). This helps in tracking and auditing for compliance purposes.  
* *Data Integrity and Consistency*: Ensure that data exchanged between systems is accurate and consistent. Implement validation checks and error handling mechanisms to maintain data integrity.  
* *Operational Resilience:* Develop and test contingency plans to ensure the API(s) can handle disruptions and maintain service continuity. This includes disaster recovery and business continuity planning.

## **Hypothesis of Success and Metrics** {#hypothesis-of-success-and-metrics}

### **Assumptions** {#assumptions}

1. *Interoperability:* Design the API for use with different check deposit products, regardless of their underlying technologies, using standardized data formats and protocols.  
2. *Scalability:* Handle varying loads and scale as needed to accommodate growth in transaction volumes and the addition of new banking cores/systems of record.  
3. *Security:* Protect sensitive financial data by using encryption, secure authentication, and authorization mechanisms.  
4. *Compliance:* Comply with relevant regulatory requirements and industry standards, such as GDPR, CFPB, and financial regulations specific to the regions where the systems operate.  
5. *Reliability and Resilience:* Ensure high availability and reliability, with mechanisms for failover and disaster recovery to maintain service continuity.  
6. *Performance:* Deliver high performance with minimal latency to ensure efficient processing of transactions and data exchanges.  
7. *Comprehensive Documentation:* Offer detailed developer documentation so they can understand how to use the API effectively, including API endpoints, data models, authentication methods, and error handling.  
8. *Monitoring and Analytics:* Implement monitoring and analytics tools for tracking the API’s performance, detecting issues, and providing insights for continuous improvement.  
9. *Flexibility and Extensibility:* Accommodate for future enhancements and integrations with additional systems (such as additional check deposit products or core banking systems) without requiring significant rework.

### **Metrics** {#metrics}

| What to Measure | How to Measure | Target |
| :---- | :---- | :---- |
| Performance | For **response time** (latency), measure the time it takes for the API to return a response/results. For **throughput** (requests per second – RPS), track the number of requests successfully processed per second. For **peak load handling**, track the maximum requests per second that the API handle before performance degrades. For **system of record/database query performance**, determine the average execution time for fetching data/information from the SOR/DB. | 2 seconds for 95% of requests under normal load X number of requests X requests per second (RPS) X amount of time for image upload and posting the deposit to the appropriate banking core |
| Reliability and Availability | For **uptime**, measure the percentage of uptime to ensure continuous availability. For **error rate**, measure the percentage of failed requests out of the total of API calls. For **timeout rate**, determine the number of requests that time out due to slow responses from downstream services such as core banking systems/systems of record. | 99.99% uptime X percentage of failed requests X number of requests  |
| Security | For **unauthorized access attempts**, track the number of failed authentication or authorization requests. For **data encryption compliance**, ensure all responses use TLS 1.2+ and sensitive data is encrypted at rest. For **audit log completeness**, measure whether all sensitive API interactions are logged for compliance. | X number of unauthorized access attempts 100% compliance X number logged |
| User Experience | For **caching**, measure the percentage of requests served from the cache instead of querying the core banking system/system of record. For **API versioning**, track how many clients are using older versions of APIs versus the latest version. | X% of requests served from the cache  X number of clients |
| Resource Utilization | For **CPU and memory usage**, ensure API servers are not overutilized or underutilized. For **database load**, track the query load and response times from core banking systems/systems of record. | Need proper metrics here.  |

## **Dependencies** {#dependencies}

| No. | Team | Contacts | Requirement |
| :---- | :---- | :---- | :---- |
| DR-1 | D1 Flex Product  | Mac Glore, D1 PM Numan Hammoudeh, D1 PO | Provide D1 Flex mobile product requirements to API product manager (Jen).  Review and approve this PRD. Coordinate timelines/milestones between D1 journey team assigned and the Open Banking journey team assigned. |
| DR-2 | Digital and Open Banking Architecture | TBD, Ent Arch TBD, App Arch | Provide enterprise guidance on Open Banking architecture needs Provide application/API guidance on Open Banking needs |

## **Schedule and Milestones \= TBD** {#schedule-and-milestones-=-tbd}

| Milestone | Description | Desired Date | Go/No-Go |
| :---- | :---- | :---- | :---- |
| MVP/ phase 1 / etc. | Describe what work is contained in this milestone | Provide deliver date or other pertinent dates | Lay out what metrics or decisions are needed to make the go/no-go decision |
|  |  |  |  |


## Glossary

- **API:** Application Programming Interface; a set of rules for interacting with software components.
- **Audit Trail:** A record of all actions and changes for compliance and security purposes.
- **Check Deposit:** The process of submitting a check for deposit via mobile or digital channels.
- **D1 Flex Mobile:** FIS’s mobile banking platform for retail consumers and small businesses.
- **Deposit Limit:** The maximum amount or number of deposits allowed per user or account in a given period.
- **Eligibility:** Criteria that determine whether a user or account can access mobile check deposit features.
- **Epic:** A large body of work that can be broken down into multiple user stories.
- **IBS/HORIZON:** Core banking systems integrated via Open Banking APIs.
- **Open Banking:** A system that allows third-party access to financial data via APIs for innovation and integration.
- **RDC (Remote Deposit Capture):** Technology enabling checks to be deposited remotely using digital images.
- **SDK:** Software Development Kit; tools and libraries for integrating with APIs.
- **Status:** The current state of a deposit (e.g., Accepted, Rejected, Pending, On Hold).
- **User Story:** A short, simple description of a feature told from the perspective of the user.

### **Business Risks** {#business-risks}

* Loss of competitive advantage  
  * Competitors and fintechs offer better APIs/integration. They might offer seamless API integration that could attract more partners/customers.  
  * Reduced innovation opportunities. Without an orchestrated API, launching new mobile check deposit capabilities becomes harder.  
* Limited revenue growth  
  * Fewer API-driven partnerships. Without a unified check deposit API, banks, fintechs, and businesses cannot easily integrate with FIS’ Open Banking platform limiting potential future partnerships.  
  * Missed open banking opportunities. Regulations like Open Banking (USA, UK) and PSD2 (Europe) encourage API-based data sharing. Without an orchestrated set of process/experience APIs, FIS could miss out on API monetization and compliance-driven partnerships.

**Technical/Operational Risks**

* Increased complexity and inefficiency  
  * Developers must integrate to multiple APIs. Without orchestration/mediation/standardization, developers have to call multiple backend services separately (e.g. one API for accounts, another for balances), increasing development effort and complexity.  
  * Increased backend load. Multiple direct requests to core banking systems/systems of record (instead of a single orchestrated call) can strain backend resources, reducing overall system performance.  
* Higher maintenance costs  
  * More API calls equal higher infrastructure costs. Instead of a single optimized API handling multiple request efficiently, developers would need to manage multiple inefficient requests.  
  * More custom development. Each consuming application (mobile, web, 3P integration) would need custom logic to retrieve and merge check deposit details, leading to maintenance overhead.

### **Security/Compliance Risks** {#security/compliance-risks}

* Inconsistent Security Controls  
  * Decentralized API calls have more attack surface. Without a centralized orchestrated API, individual services might expose their endpoints, increasing security risks.  
  * Harder to enforce role-based access control (RBAC). Without orchestration, different services may enforce access controls inconsistently, leading to potential unauthorized access.  
* Compliance Challenges  
  * Data privacy violations. Open banking regulations require structured access to account data including check deposits. A fragmented API approach makes compliance auditing harder.  
  * Audit and logging complexity. Instead of tracking requests through a single API, logs would be spread across multiple services, making fraud detection and compliance reporting more difficult.

## **Appendix** {#appendix}

### **Change Log** {#change-log}

| Version Number | Date | Point of Contact | Changes |
| :---- | :---- | :---- | :---- |
| 1.0 | 6/16/25 | Jen Childress | Initial first draft |
|  |  |  |  |
|  |  |  |  |

### **Glossary** {#glossary}

| Term/Acronym | Definition |
| :---- | :---- |
| FXD | Funds eXpress, an FIS non-preferred mobile check deposit product. |
| DLC | Direct Link Consumer, an FIS preferred mobile check deposit product for all new clients coming onto D1 Flex Mobile and for migration in the future for client currently using FXD. |
| RDC | Remote Deposit Capture, an industry term for the capability for offering mobile check deposit. |

### **Important Links** {#important-links}

* Digital One Flex Mobile PRD: [Deposit Check Beacon United](https://fisglobal.sharepoint.com/:w:/r/teams/PRDCollaborationandReview/Shared%20Documents/General/4.%20Top%2012%20Competitive/PRD%20-%20Deposit%20Check%20Beacon%20United.docx?d=w18f6a582f1ce46c38811707358a24d30&csf=1&web=1&e=DHP4Ws)

### **Open Questions** {#open-questions}

* For the Q3 release, will we need to integrate to FXD and DLC? Or just FXD?   
  *Answer:  FXD for Q3 and then fast follow with DLC*

