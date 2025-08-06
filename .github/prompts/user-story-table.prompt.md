# Table-Based User Story Prompt

Review the selected file and expand on the user story by adding a table definition based on the provided template. Use the guidelines and template below to structure your response.

## Guidelines

1. Think about what data would be most valuable to display in the table.
2. Consider the logical user actions that should be supported (e.g., edit, delete, search, etc.).
3. Define clear and concise column names.
4. Ensure the table is user-friendly and accessible.
5. Use appropriate data types for each column to enhance usability. 
6. Include blank lines around headings and sections for better readability and markdown linting.

## Template

```markdown
### Table Columns

list of columns in the table, including:
- Selection Column (optional, allows bulk actions on selected rows)
- Data Column 1 Name - data type (input, dropdown, checkbox, pill, etc.)
- Data Column 2 Name - data type (input, dropdown, checkbox, pill, etc.)
- Data Column 3 Name - data type (input, dropdown, checkbox, pill, etc.)
- Pencil (optional, edit record action) - icon
- Trash (optional, delete record action) - icon
- Action Dots (optional, menu of secondary actions)

#### Table Filters

[List of filterable columns]

#### Table Pagination

[Number of records per page (e.g., 10, 20, 50)]

#### Table Sorting

[List of sortable columns]

#### Table Actions

List of actions available for the table or bulk actions, such as:
- Search (list of searchable columns)
- Add new record
- Export data
- Bulk Edit
- Bulk Delete
```