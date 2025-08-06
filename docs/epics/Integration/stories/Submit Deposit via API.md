# Story: Submit Deposit via API

## Jira Story: [Link to Jira story]

### User Story

**AS AN** external developer  
**I WANT TO** submit a check deposit using the API  
**SO THAT** my app can initiate mobile check deposits for users

### Acceptance Criteria

**GIVEN** valid check images, account info, and deposit amount  
**WHEN** I call the deposit submission endpoint  
**THEN** the system accepts the deposit and returns a transaction ID

### Dependencies

- RDC product APIs
- Deposit submission endpoint
- User authentication

### Open Questions

- What image formats and data are required for submission?
- How is the transaction ID structured?
