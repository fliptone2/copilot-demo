# Epic: RDC Abstraction

## Jira Epic: [Link to Jira epic]

### Description

Abstract differences between remote deposit capture (RDC) products, providing a unified API and experience for developers and users regardless of backend provider.

### Acceptance Criteria

1. The API normalizes check deposit submission, status, and error handling across RDC products.
2. Product-specific features (e.g., batch processing, cutoff times) are supported via configuration.
3. Developers do not need to manage RDC-specific logic in their applications.
4. The system maintains a consistent transaction ID and audit trail across all RDC integrations.

### Dependencies

- Integration epic
- Core banking and RDC provider APIs
- Maintainability & Observability epic

### Open Questions

- What RDC products must be supported at launch?
- How are new RDC products added to the abstraction layer?
- Are there limitations to feature parity across RDC products?
