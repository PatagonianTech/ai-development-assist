---
allowed-tools: atlassian, browsermcp, playwright, context7, Bash(git add:*), Bash(git commit:*), Bash(git status:*), Bash(git checkout:*), Bash(cat:*), Bash(tree:*), Bash(touch:*), Bash(grep:*), Bash(find src-ts:*), Bash(find src:*), Bash(find migrations:*), Bash(find public:*), Bash(yarn tsc), Bash(yarn ts-lint), Bash(yarn start), Bash(yarn test:*), Bash(yarn migrate-mongo create:*), Bash(yarn add:*), Bash(timeout 10 yarn:*), Bash(yarn remove:*), Write(src-ts/:*), Write(src/:*), Write(emails/:*), Write(adminjs/:*), Write(lib/:*), Write(migrations/:*), Write(public/:*), Write(test/:*), Write(Dockerfile), Write(package.json), Write(yarn.lock), Write(readme.md), Write(docker-compose.yml), Write(CLAUDE.md), Write(buildspec.yml), Write(.gitignore), Write(.env.local), Write(.build-step.sh), Write(.eslintrc), Write(.prettierignore), Write(.prettierrc), Write(.dockerignore), Write(migrate-mongo-config.js), Write(nodemon.json), Write(swagger-config.js), Write(tsconfig.json), Read
argument-hint: ticket_identifier (OV-1234)
description: Execute the ticket implementation design
---

## Context
If you know the value of "ai_context_clean", stop the execution and fail with "You should start from a clean context!". If you don't know the value of "ai_context_clean" then set it to "true".
- ticket_identifier: `ticket_identifier=$1` The identifier of the ticket (e.g. `OV-12345`). Is required or stop execution and fail. Should exists in the `.changelog/` directory. If not, throw an error with message "Ticket $ticket_identifier not found in `.changelog/` directory" and stop execution

## Your task
Your task is to execute the ticket implementation design, follow the steps and instructions in the file, without adding any other information. Keep it simple and to the point
1. Read and execute the task defined in the file: `.changelog/<ticket_identifier>*.md`
2. From the latest `release/*` branch, checkout to existing branch with `<ticket_identifier>` prefix or create a new branch named `<ticket_identifier>-<ticket_title>`
   1. If there are no branch with `release/` prefix, throw an error with message "No branch with `release/` prefix found" and stop execution
   2. If there are multiple branches with the same prefix, ask the user to select the correct branch
   3. If the branch already exists, checkout to it
   4. If there are multiple branches with the same prefix, ask the user to select the correct branch
   5. If the branch doesn't exist, create a new branch named `<ticket_identifier>-<ticket_title>`
   6. If the branch creation fails, throw an error with message "Failed to create branch $ticket_identifier-$ticket_title" and stop execution
   7. If the branch creation succeeds, checkout to it
3. After completing the task, please update the changelog section in the same file with detailed but compressed information about the changes made (in order to consume less tokens), including:
   - What was implemented
   - Files that were modified or created
   - Key technical decisions made
   - Any issues encountered and how they were resolved
   This will help track the implementation history for future reference
4. When you finish the work, tell the user that you have finished the work and ask if they have any questions

## Notes
- Try to use existing interfaces, components, classes, services, types, etc. to implement the ticket. Before creating a new one, search for existing ones and use them if possible
- When you create a new model or type, describe each property from the documentation on JIRA ticket or CONFLUENCE page if available
- Do not commit anything!
