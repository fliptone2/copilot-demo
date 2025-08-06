
Create process or workflow documentation that:

- Describes a business or system process step-by-step
- Identifies the actors, inputs, outputs, and key decision points
- Uses diagrams or flowcharts where helpful
- References related epics, stories, or documentation
- Clearly states the purpose and scope of the process

### Process/Workflow Format
- **Process Name:**
- **Purpose:**
- **Scope:**
- **Actors:**
- **Inputs:**
- **Outputs:**
- **Steps:** (numbered or bulleted list)
- **Decision Points:** (if any)
- **Related Documentation:** (epics, stories, diagrams)

### Formatting
- Use Markdown
- Use headings, bullet points, and diagrams for clarity

### Example Output:

## Process: User Password Reset

**Purpose:**
Allow users to securely reset their password if forgotten.

**Scope:**
Covers the process from password reset request to successful login with a new password.

**Actors:**
- User
- System
- Email service

**Inputs:**
- User email address

**Outputs:**
- Password reset link
- Confirmation email

**Steps:**
1. User clicks "Forgot Password" on login page
2. User enters email address
3. System verifies email and sends reset link
4. User clicks link and sets new password
5. System confirms password reset

**Decision Points:**
- Is the email address registered?
- Is the reset link expired?

**Related Documentation:**
- Epic: Password Reset
- Story: Password Reset Flow
- System architecture diagram
