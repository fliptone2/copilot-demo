# Story: Capture Check Images

## Jira Story: [Link to Jira story]

### User Story

**AS A** mobile banking user  
**I WANT TO** capture front and back images of a check using my device's camera  
**SO THAT** I can deposit the check digitally

### Acceptance Criteria

**GIVEN** I am authenticated and on the mobile check deposit screen  
**WHEN** I use the camera to take photos of the front and back of my check  
**THEN** the system saves the images for review and submission

### Dependencies

- Mobile device camera access
- Deposit management module


### Form Title

- Capture New Check Images
- View Captured Check Images
- Edit Captured Check Images

### Form Fields

### Form Row 1

- Check Front Image - file upload (image)

### Form Row 2

- Check Back Image - file upload (image)

### Form Row 3

- Image Quality Status - text (plain text, read-only)

### Form Row 4

- Capture Date - datepicker (plain text)
- Captured By - text (plain text)

### Form Action Bar

- Capture - button (primary)
- Retake - button (secondary)
- Save - button (primary)
- Cancel - button (secondary)

### Open Questions

- What image formats and resolutions are supported?
- Are there device-specific camera limitations?
- Should image quality be displayed before saving?
