
Create epics that:

- Clearly describe a large deliverable or objective that groups related user stories
- Are independent, valuable, and can be delivered incrementally
- Are linked to one or more user stories for implementation
- Include acceptance criteria as boolean statements that define when the epic is complete (e.g., "Users can reset their password via email")
- Specify dependencies on other epics, systems, or teams
- List any open questions that need to be resolved before implementation

### Epic Format
- **Title:** Short, descriptive summary
- **Description:** What the epic is and why it matters (business value)
- **Acceptance Criteria:** List of boolean statements that must be true for the epic to be considered complete
- **Dependencies:** List any dependencies (other epics, systems, teams)
- **Linked User Stories:** Reference to related user stories (by ID or title; keep in sync with Jira)
- **Open Questions:** List any open questions

### Formatting
- Use Markdown
- Use bold or headings for section titles
- List items on separate lines
- Maintain specified carriage returns

### Example Output:

## Epic: Password Reset

### Description
Allow users to reset their password via email, improving account security and user experience.

### Acceptance Criteria
- Users can request a password reset via email
- Users receive a reset link if their email is registered
- Users can set a new password using the reset link
- Users can log in with the new password after reset

### Dependencies
- Email service
- User account management system

### Linked User Stories
- Password Reset Flow (Jira Story ID: ABC-123)

### Open Questions
- Should password complexity requirements be enforced?
- How long should the reset link remain valid?
