# Form-Based User Story Prompt

Review the selected file and expand on the user story by adding a form definition based on the provided template. Also create three acceptance criteria that are specific to the form's create, view, and edit functionality. Use the guidelines and template below to structure your response.

## Guidelines

1. Think about what data would be most valuable to display in the form.
2. Consider the logical user actions that should be supported (e.g., edit, delete, search, etc.).
3. Define clear and concise field names.
4. Ensure the form is user-friendly and accessible.
5. Use appropriate data types for each field to enhance usability.
6. Include blank lines around headings and sections for better readability and markdown linting.

## Template

```markdown
### Form Title

[Provide three clear and descriptive titles for the form for each mode (create, view details, or edit), e.g., "Create New Customer," "View Customer Details," "Edit Customer."]

### Form Fields
[
    - In general, each field should have it's own row unless it is part of a logical group like "City," "State," and "Zip Code." or "First Name" and "Last Name" (where each is displayed as its own bullet).
    - For each row in the form, create a Form Row heading ("### Form Row 1").
    - Created By, Created Date, Last Modified By, and Last Modified Date should always be displayed as plain text.
    - Valid data types for form fields include:
        - text (single-line text)
        - number (numeric input)
        - email (email input)
        - multiline (multi-line text)
        - select (single or multi-select)
        - checkbox (boolean)
        - radio (single choice)
        - datepicker (date selection)
]

- Field 1 Name - data type (text, select, checkbox, etc.)
- Field 2 Name - data type (text, select, checkbox, etc.)
- Field 3 Name - data type (text, select, checkbox, etc.)

### Form Action Bar

[list the actions available for the form, such as:
- Save - button type (primary, secondary, etc.)
- Cancel - button type (primary, secondary, etc.)
- Delete (if applicable) - button type (primary, secondary, etc.)
- Deactivate (if applicable, e.g., for user accounts) - button type (primary, secondary, etc.)
- Reactivate (if applicable, e.g., for deactivated user accounts) - button type (primary, secondary, etc.)
- Submit (if applicable, e.g., for forms that require submission) - button type (primary, secondary, etc.)
]