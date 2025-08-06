# Story: View/Edit Customer

## Jira Story: [Link to Jira story]

### User Story

**AS A** bank employee  
**I WANT TO** view and edit the customer information associated with a deposit entry  
**SO THAT** I can ensure customer records are accurate and up-to-date for compliance and customer support


### Acceptance Criteria

**Create:**

- **GIVEN** a bank employee is authenticated and has access to the deposit management module  
  **WHEN** the employee initiates the creation of a new customer record for a deposit entry  
  **THEN** the system displays a blank customer form, validates required fields, and saves the new customer with an audit trail entry.

**View:**

- **GIVEN** a deposit entry with an associated customer and the bank employee is authenticated and has access to the deposit management module  
  **WHEN** the employee views the customer information for the deposit entry  
  **THEN** the system displays all current customer details in a read-only form, including audit trail information.

**Edit:**

- **GIVEN** a deposit entry with an associated customer and the bank employee is authenticated and has access to the deposit management module  
  **WHEN** the employee edits permitted customer fields and saves changes  
  **THEN** the system updates the customer details, restricts edits to non-editable fields, and records the change in the audit trail.

### Form Title

Edit Customer Details

### Form Fields

### Form Row 1

- Customer ID - text (read-only)

### Form Row 2

- First Name - text
- Last Name - text

### Form Row 3

- Email Address - email

### Form Row 4

- Phone Number - text

### Form Row 5

- Address Line 1 - text
- Address Line 2 - text

### Form Row 6

- City - text
- State - text
- Zip Code - text

### Form Row 7

- Account Number - text (read-only)

### Form Row 8

- Customer Status - select (Active, Inactive, Suspended)

### Form Row 9

- Created By - text (plain text)
- Created Date - datepicker (plain text)
- Last Modified By - text (plain text)
- Last Modified Date - datepicker (plain text)

### Form Action Bar

- Save - button (primary)
- Cancel - button (secondary)
- Delete - button (secondary)
- View Audit Trail - button (secondary)

### Dependencies

- Manage Deposit Entry story
- Integration with customer database or API
- User authentication and authorization

### Open Questions

- Which customer fields are editable from the deposit entry context?
- Should edits to customer data here update the master customer record or only the deposit entry's snapshot?
- Is there a need to restrict edits based on customer or deposit status?
- How is the audit trail for customer changes maintained and accessed?
