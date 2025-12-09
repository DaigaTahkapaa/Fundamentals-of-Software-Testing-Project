## Summary
Misleading and redundant validation error messages when creating a project with a name exceeding 255 characters.

## Steps to reproduce
1. Navigate to https://gitlab.com/projects/new#blank_project
2. Enter a project name longer than 255 valid characters (e.g., 256 A's)
3. Click "Create project" button

## What is the current bug behavior?
The form displays 7 error messages:
- Project namespace name is too long (maximum is 255 characters)
- Project namespace path is too long (maximum is 255 characters)
- Project namespace path can contain only letters, digits, '_', '-' and '.'. Cannot start with '-', end in '.git' or end in '.atom'
- Name is too long (maximum is 255 characters)
- Path can contain only letters, digits, '_', '-' and '.'. Cannot start with '-', end in '.git' or end in '.atom'
- Path is too long (maximum is 255 characters)
- Path is too long (maximum is 255 characters)

Issues:
1. The "can contain only letters, digits..." error appears even though only letters were entered
2. "Path is too long" message appears twice (duplicate)
3. Multiple cascading errors when the root cause is simply that the name exceeded 255 characters

## What is the expected correct behavior?
A single, clear error message such as:
- "Name is too long (maximum is 255 characters)"

Or a consolidated message explaining that the name length also affects the auto-generated path.

## Relevant logs and/or screenshots
```html
<div class="gl-alert gl-mb-5 gl-alert-danger gl-alert-not-dismissible gl-alert-has-title" id="error_explanation" role="alert">
  <ul class="gl-pl-5 gl-mb-0">
    <li>Project namespace name is too long (maximum is 255 characters)</li>
    <li>Project namespace path is too long (maximum is 255 characters)</li>
    <li>Project namespace path can contain only letters, digits, '_', '-' and '.'. Cannot start with '-', end in '.git' or end in '.atom'</li>
    <li>Name is too long (maximum is 255 characters)</li>
    <li>Path can contain only letters, digits, '_', '-' and '.'. Cannot start with '-', end in '.git' or end in '.atom'</li>
    <li>Path is too long (maximum is 255 characters)</li>
    <li>Path is too long (maximum is 255 characters)</li>
  </ul>
</div>
```
![Error messages triggered by too long name](/Image/04_ProjectPage_CascadingErrors.png)

## Possible fixes
Review the validation logic to:
- Remove duplicate error messages
- Only show relevant validation errors (not character restrictions when input contains only valid characters)
- Consider consolidating related errors into a single meaningful message

## Whom do you report/ Assign To/ Tags
/label ~bug ~UX ~validation
/cc @project-manager
/assign @qa-tester

## Priority
Minor - The validation works (prevents creation), but the error messages are confusing and unhelpful to users.
