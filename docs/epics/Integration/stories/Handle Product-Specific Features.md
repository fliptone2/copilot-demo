# Story: Handle Product-Specific Features

## Jira Story: [Link to Jira story]

### User Story

**AS AN** external developer  
**I WANT TO** use product-specific features (e.g., batch processing, cutoff times) via the API  
**SO THAT** my integration supports all required RDC product capabilities

### Acceptance Criteria

**GIVEN** a supported RDC product and feature  
**WHEN** I call the relevant API endpoint with required parameters  
**THEN** the system processes the request according to product-specific logic

### Dependencies

- RDC product APIs
- API documentation for product features

### Open Questions

- What product-specific features are exposed?
- How are feature parameters documented?
