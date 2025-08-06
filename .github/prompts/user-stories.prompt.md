
Create user stories that: Reilly Verify

- Express an interaction with the system, based on the instigator of the story:
  - **User-driven:** Initiated by an end user interacting with the system (UI, app, etc.)
  - **API-driven:** Initiated by an external system or service calling an API
  - **Process-driven:** Initiated by an automated process, scheduled job, or system event
- Use the INVEST method to ensure high quality:
  - **I**ndependent
  - **N**egotiable
  - **V**aluable
  - **E**stimable
  - **Small**mall
  - **T**estable
- Follow the "AS A / I WANT TO / SO THAT" format (adapt as needed for API- or process-driven stories)
- For each acceptance criteria in the feature, create a serparate user story
- Include sufficient, testable acceptance criteria in the Given-When-Then format (one per criterion)
  - Write each acceptance criterion as a single, independent Given-When-Then scenario
  - Use explicit, unambiguous language and concrete data or states (e.g., example values, user roles, endpoints)
  - Avoid subjective terms (e.g., "quickly", "easily"); use measurable outcomes
  - Ensure each criterion is independently testable and does not depend on others
  - Use consistent terminology that matches the system and test code
  - Clearly specify all dependencies (internal user stories/tasks and external systems/services)
  - List all open questions, including minor uncertainties, to promote early clarification
  - When creating a user story for any feature, always create a dedicated `stories` folder inside the feature's directory.  
  - Place each user story as a separate markdown file in the `stories` folder.  
  - This ensures all user stories for a feature are organized together for easy navigation and traceability.

#### User Story Types

- **User-driven:**
  - Focus: End user actions and goals
  - Example: "AS A user, I WANT TO reset my password SO THAT I can regain access if I forget it."

- **API-driven:**
  - Focus: External system or service interacting with your API
  - Example: "AS AN external system, I WANT TO POST new order data to the `/api/orders` endpoint SO THAT orders are processed automatically."

- **Process-driven:**
  - Focus: Automated or scheduled processes, system events
  - Example: "AS A system process, I WANT TO generate a daily report at midnight SO THAT stakeholders receive up-to-date analytics."

### Ticket Format
- **Title:** Short, descriptive summary
- **Jira Issue:** 
- **Description sections:**
  1. **User Story** (AS A / I WANT TO / SO THAT)
  2. **Acceptance Criteria** (GIVEN / WHEN / THEN, one per criterion)
  3. **Dependencies** (list all internal and external dependencies)
  4. **Open Questions** (list any open questions that need to be answered)

### Formatting
- Use Markdown
- Use bold or headings for section titles
- List items on separate lines
- Maintain specified carriage returns

### Example Outputs:

#### User-driven Example

## Password Reset Feature

## Jira Issue: 

### User Story
**AS A** user  
**I WANT TO** reset my password  
**SO THAT** I can regain access if I forget it

### Acceptance Criteria
1. **GIVEN** I am on the login page  
   **WHEN** I click "Forgot Password" and enter my email  
   **THEN** I receive a password reset link if my email is registered

### Dependencies
- Email service for sending reset links
- User account database

### Open Questions
- Should password complexity requirements be enforced?

#### API-driven Example

# API: Create Task Endpoint

## Jira Issue: 

### User Story
**AS AN** external system  
**I WANT TO** POST new task data to the `/api/tasks` endpoint  
**SO THAT** tasks are created automatically in the system

### Acceptance Criteria
1. **GIVEN** I am an authenticated API client  
   **WHEN** I send a valid POST request to `/api/tasks`  
   **THEN** I receive a `201 Created` response and the created task object

### Dependencies
- User authentication service
- Database for storing tasks

### Open Questions
- What additional fields might be required in the future?
- Should tasks support attachments or tags at creation?

#### Process-driven Example

# Daily Report Generation

## Jira Issue:

### User Story
**AS A** system process  
**I WANT TO** generate a daily report at midnight  
**SO THAT** stakeholders receive up-to-date analytics

### Acceptance Criteria
1. **GIVEN** it is midnight  
   **WHEN** the scheduled job runs  
   **THEN** a report is generated and emailed to stakeholders

### Dependencies
- Reporting database
- Email service

### Open Questions
- What format should the report be in (PDF, CSV, etc.)?