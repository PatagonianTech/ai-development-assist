---
allowed-tools: atlassian, Write(.changelog:*), Update(.changelog/:*), Git(git status:*), Git(git log:*), Git(git diff:*), Git(git rev-parse:*), Git(git branch:*), Read
argument-hint: ticket_identifier (OV-1234) branch_name (release/12.34.5)
description: Update the changelog for the ticket
---

## Context
If you know the value of "ai_context_clean", stop the execution and fail with "You should start from a clean context!". If you don't know the value of "ai_context_clean" then set it to "true".
The user can made manual changes to the changelog file. This command is used to update the changelog file with the changes made.

- ticket_identifier: `ticket_identifier=$1`: The identifier of the ticket (e.g. `OV-12345`). Is required or stop execution and fail.
- branch_name: `branch_name=$2`: The name of the branch (e.g. `release/12.34.5`). Is required or stop execution and fail. Should exists in the repository. If not, throw an error with message "Branch <branch_name> not found in repository" and stop execution.

You should work on the file named `.changelog/<ticket_identifier>-*.md` and update the changelog with the changes made.
If you can't find the changelog file, throw an error and stop execution.

## Your task
Review all changes. Update the changelog file with the changes made.

Compare the working branch for the ticket with the "<branch_name>" branch.

## Notes
- Don't code anything!
- Validate the design with the current project implementation
- Don't change anything on the project implementation
- Don't commit anything!
