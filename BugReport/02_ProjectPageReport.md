Summary

Multiple issues detected during testing of Registration, Project Creation, and Issue Management pages.
These issues include missing validation messages, incorrect behavior on duplicate creation attempts, and acceptance of invalid inputs.

Steps to reproduce
Bug 1 — Registration Page: Missing password validation

Navigate to: https://gitlab.com/users/sign_up

Enter a valid email

Enter a valid username

Leave the password field empty

Submit the registration form

Bug 2 — Project Page: Duplicate project name not validated

Navigate to: https://gitlab.com/projects/new

Create a blank project named “MyFirstProject”

Return to project creation page

Enter the same project name “MyFirstProject”

Submit the form

Bug 3 — Issue Page: Duplicate issue title accepted

Navigate to new issue creation page

Create an issue with title “Updated First Issue”

Return to new issue creation

Enter the same issue title “Updated First Issue”

Submit the form

What is the current bug behavior?
Bug 1 — Registration Page

No error message appears after submitting the form with an empty password field.
The page refreshes silently without user feedback.

Bug 2 — Project Page

Creating a project with an already existing name does not show the expected validation message.
The system reloads the page without explaining the error.

Bug 3 — Issue Page

A duplicate issue title is accepted and created successfully without any validation message.
The system treats duplicate titles as valid.

What is the expected correct behavior?
Bug 1

A clear validation message should appear:
"Password can't be blank."

Bug 2

System should prevent duplicate project names and show:
"Name has already been taken."

Bug 3

System should reject duplicate issue titles and display:
"Title has already been taken."

Relevant logs and/or screenshots

N/A — All issues are UI validation/functional behavior.

Possible fixes
Bug 1 — Registration Page

Add client-side and backend validation for required password

Display validation error under the password field

Bug 2 — Project Page

Ensure server validation errors are returned and displayed in UI

Improve frontend error handling for duplicate name responses

Bug 3 — Issue Page

Add unique title validation to issue model

Display validation errors on issue creation form

Whom do you report / Assign To / Tags

Assign To:

Registration Team

Project Management Team

Issue Tracking Team

Tags:
Register, ProjectCreation, IssueManagement, Validation, Bug

Priority

Bug 1 (Registration) — High

Bug 2 (Project) — Medium

Bug 3 (Issue) — Medium