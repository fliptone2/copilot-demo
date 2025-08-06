# Epic: RDC Abstraction

## Jira Epic: [Link to Jira epic]

### Description

Abstract remote deposit capture product-specific logic, status mapping, and formatting within the orchestration layer to provide a unified integration experience for developers.

### Acceptance Criteria

1. Orchestration layer handles RDC product-specific logic and formatting.
2. Status mapping is unified across RDC products.
3. Developers interact with a single, consistent API.
4. Changes to RDC products do not require consuming app changes.

### Dependencies

- Orchestration layer implementation
- RDC product documentation
- API versioning strategy

### Open Questions

- How is status mapping managed for new RDC products?
- What changes require orchestration layer updates?
- How is backward compatibility ensured?
