# Prompt: Create Jira Epic from Selected Markdown File

Review the selected file and use it as the source for a new Jira epic.

## Guidelines
1. Parse the markdown to extract the user story, acceptance criteria, dependencies, and open questions.
2. Create a new Jira epic using this information.
3. After the Jira epic is created, update the markdown file by inserting the Jira epic number in the "Jira Epic" section.
4. Save the updated markdown file.
5. Confirm completion and provide the Jira issue key.

## Constraints
- Only use the currently selected markdown file as the source.
- Do not create duplicate Jira stories for the same file.
- Ensure the Jira issue number is clearly visible in the markdown file after update.