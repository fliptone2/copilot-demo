
Review the selected file and use it to create features for the chosen epic. The stories should be structured, clear, and follow the provided template. Each story should encapsulate a discrete interaction that can be turned into development tasks. 

# Story Creation Guidelines
Give each story a short title (e.g., "Create New User"). Create each story in a separate Markdown file that lives in the "stories" folder beneath the epic. Name the file after the story title. Using the provided template to create stories that:

- Express an interaction with the system, based on the actor in the story:
  - **User-driven:** Initiated by an end user interacting with the system (UI, app, etc.)
  - **API-driven:** Initiated by an external system or service calling an API
  - **Process-driven:** Initiated by an automated process, scheduled job, or system event
- Use the INVEST method to ensure high quality:
  - **I**ndependent
  - **N**egotiable
  - **V**aluable
  - **E**stimable
  - **Small**mall
  - **T**estable
- Follow the "AS A / I WANT TO / SO THAT" format (adapt as needed for API- or process-driven stories)
- Include one, testable acceptance criteria in the story in the Given-When-Then format
  - Write each acceptance criterion as a single, independent Given-When-Then scenario
  - Use explicit, unambiguous language and concrete data or states (e.g., example values, user roles, endpoints)
  - Avoid subjective terms (e.g., "quickly", "easily"); use measurable outcomes
  - Use consistent terminology that matches the system and test code
- Clearly specify all dependencies (internal user stories/tasks and external systems/services)
- List all open questions, including minor uncertainties, to promote early clarification

## Formatting
- Use Markdown
- Use bold or headings for section titles
- List items on separate lines
- Leave a blank line between sections
- Use bullet points for clarity
- Use numbered lists for acceptance criteria
- Maintain specified carriage returns

## Story Template
```markdown
# Story: [Story Title]

## Jira Issue: [Link to Jira issue if applicable]

### User Story
**AS A** [user role]  
**I WANT TO** [goal]  
**SO THAT** [reason]

### Acceptance Criteria
**GIVEN** [initial state]  
**WHEN** [action taken]  
**THEN** [expected outcome]

### Dependencies
- [List all internal and external dependencies, e.g., other user stories, systems, teams]
- [List any external APIs, services, or systems that this story depends on]

### Open Questions
- [List any open questions that need resolution based on the current story description]
```
