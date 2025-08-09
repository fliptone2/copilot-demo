# Epic: Error Handling & Retry

## Jira Epic: [Link to Jira epic]

### Description

Implement robust error handling, clear user messaging, and automatic retry logic for failed check deposit submissions, ensuring a user-friendly and resilient experience.

### Acceptance Criteria

1. Users receive clear, actionable error messages for failed deposits.
2. System returns normalized error codes for all failure scenarios.
3. Automatic retry logic is implemented for transient failures.
4. User-friendly guidance is provided for error resolution.

### Dependencies

- Integration & Sandbox epic
- RDC Abstraction epic
- Notification service

### Open Questions

- What is the retry policy for failed submissions?
- How are persistent errors escalated to support?
