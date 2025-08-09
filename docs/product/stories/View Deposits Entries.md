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

- Selection Checkbox - checkbox (for bulk actions)
- Deposit ID - text
- User/Account - text
- Amount - currency
- Status - pill (e.g., Pending, Approved, Rejected)
- Submitted Timestamp - datetime
- Processed Timestamp - datetime
- Pencil (Edit Deposit) - icon
- Trash (Delete Deposit) - icon
- Action Dots (More Actions) - icon

#### Table Filters

- Status
- User/Account
- Date Range (Submitted Timestamp)
- Amount Range

#### Table Pagination

- 20 records per page

#### Table Sorting

- Deposit ID
- User/Account
- Amount
- Status
- Submitted Timestamp
- Processed Timestamp

#### Table Actions

- Search (Deposit ID, User/Account)
- Add new deposit record
- Export data (CSV, Excel)
- Bulk Edit
- Bulk Delete