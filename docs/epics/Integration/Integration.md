# Epic: Integration

## Jira Epic: [Link to Jira epic]

### Description

Provide seamless integration with core banking systems, remote deposit capture providers, and third-party services to enable end-to-end mobile check deposit functionality.

### Acceptance Criteria

1. The system integrates with multiple core banking systems (e.g., IBS, HORIZON).
2. The API supports integration with both FIS and non-FIS remote deposit capture products.
3. Third-party fintech apps can access mobile check deposit features via open APIs.
4. Integration points are documented and versioned for maintainability.

### Dependencies

- Core banking and RDC provider APIs
- Documentation & SDKs epic
- RDC Abstraction epic

### Open Questions

- What are the supported integration protocols and standards?
- How is API versioning managed?
- Are there certification requirements for third-party integrators?
