# Epic: RDC Abstraction

## Jira Epic: [Link to Jira epic]

### Description

Abstract differences between remote deposit capture (RDC) products, handling product-specific logic, status mapping, and formatting within the orchestration layer for a seamless developer experience.

### Acceptance Criteria

1. API abstracts all RDC product-specific behaviors.
2. Status and error codes are normalized across products.
3. Routing logic is implemented for multiple RDC providers.
4. Developers do not need to manage RDC-specific logic.

### Dependencies

- Integration & Sandbox epic
- Core banking systems
- Open Banking architecture

### Open Questions

- What RDC products must be supported at launch?
- How is new RDC product support added?
