# Story: Poll Deposit Status

## Jira Story: [Link to Jira story]

### User Story

**AS AN** external developer  
**I WANT TO** poll the status of a submitted deposit  
**SO THAT** I can display real-time updates to users

### Acceptance Criteria

**GIVEN** a valid transaction ID  
**WHEN** I call the status polling endpoint  
**THEN** the system returns the current status of the deposit

### Dependencies

- RDC product APIs
- Status polling endpoint
- Transaction ID

### Open Questions

- What status values are supported?
- How frequently should polling occur?
