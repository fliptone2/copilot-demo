
# User Story Prompt

Review the selected file and use it to establish stories for the chosen epic. The stories should be structured, clear, and follow the provided template. Each story should encapsulate a discrete interaction that can be turned into development tasks. Use the guidelines and template below to structure your response.

## Guidelines

1. Give each story a short title (e.g., "Create New User") less than five words.
2. Provide a list of the stories that need to be created based on the chosen epic.
3. Once the stories are identified, create a structured Markdown file for each story using the provided template.
4. Create each story in a separate Markdown file that lives in the "stories" folder beneath the epic.
5. Name the file after the story title.
6. Include blank lines around headings and sections for better readability and markdown linting.
7. Using the provided template to create stories that:

    - Express an interaction with the system, based on the actor in the story:
    - **User-driven:** Initiated by an end user interacting with the system (UI, app, etc.)
    - **API-driven:** Initiated by an external system or service calling an API
    - **Process-driven:** Initiated by an automated process, scheduled job, or system event
    - Use the INVEST method to ensure high quality:
      - **I**ndependent
      - **N**egotiable
      - **V**aluable
      - **E**stimable
      - **S**mall
      - **T**estable
    - Follow the "AS A / I WANT TO / SO THAT" format (adapt as needed for API- or process-driven stories)
    - Include one, testable acceptance criteria in the story in the Given-When-Then format
    - Use explicit, unambiguous language and concrete data or states (e.g., example values, user roles, endpoints)
    - Avoid subjective terms (e.g., "quickly", "easily")
    - List all open questions, including minor uncertainties, to promote early clarification

## Template

```markdown
# Story: [Story Title]

## Jira Story: [Link to Jira story]

### User Story

**AS A** [user role]  
**I WANT TO** [goal]  
**SO THAT** [reason]

### Acceptance Criteria

**GIVEN** [initial state]  
**WHEN** [action taken]  
**THEN** [expected outcome]

### Dependencies

- [List all internal and external dependencies, e.g., other user stories, systems, features, modules]
- [List any external APIs, services, or systems that this story depends on]

### Open Questions

- [List any open questions that need resolution based on the current story description]