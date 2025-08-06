# Story: View All Deposits Table

## Jira Story: [Link to Jira story]

### User Story

**AS A** bank employee  
**I WANT TO** view a table of all mobile check deposits in the system  
**SO THAT** I can monitor deposit activity, track statuses, and support customer inquiries

### Acceptance Criteria

**GIVEN** the bank employee is authenticated and has access to the deposit management module  
**WHEN** they navigate to the deposits table view  
**THEN** the system displays a table listing all deposits, including deposit ID, user/account, amount, status, and timestamps

### Dependencies

- Status & Notifications epic
- Integration with deposit database or API
- User authentication and authorization

### Table Columns

- Selection - checkbox (bulk actions)
- Deposit ID - pill
- User Name - pill
- Account Number - pill
- Amount - pill (currency)
- Status - dropdown (Accepted, Rejected, Pending, On Hold)
- Submitted Timestamp - pill
- Updated Timestamp - pill
- Pencil - icon (edit record)
- Trash - icon (delete record)
- Action Dots - icon (secondary actions)

#### Table Filters

- Status
- User Name
- Account Number
- Submitted Timestamp (date range)
- Amount (range)

#### Table Pagination

20 records per page

#### Table Sorting

- Deposit ID
- User Name
- Account Number
- Amount
- Status
- Submitted Timestamp
- Updated Timestamp

#### Table Actions

- Search (Deposit ID, User Name, Account Number)
- Add new deposit entry
- Export data
- Bulk Edit
- Bulk Delete

### Open Questions

- What columns and filters are required in the table?
- Should export or reporting features be included?
- What is the data refresh interval for the table?
