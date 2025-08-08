# Prompt: Create Jira Story from Selected Markdown File

Review the selected file and use it as the source for a new Jira story.

## Guidelines
1. Parse the markdown to extract the user story, acceptance criteria, dependencies, and open questions.
2. Create a new Jira story using this information.
3. After the Jira story is created, update the markdown file by inserting the Jira story number in the "Jira Story" section.
4. Save the updated markdown file.
5. Confirm completion and provide the Jira issue key.

## Constraints
- Only use the currently selected markdown file as the source.
- Do not create duplicate Jira stories for the same file.
- Ensure the Jira issue number is clearly visible in the markdown file after update.