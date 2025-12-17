---
allowed-tools: atlassian, browsermcp, playwright, context7, Bash(git add:*), Bash(git commit:*), Bash(git status:*), Bash(git checkout:*), Bash(cat:*), Bash(tree:*), Bash(touch:*), Bash(grep:*), Bash(find src-ts:*), Bash(find src:*), Bash(find migrations:*), Bash(find public:*), Bash(yarn tsc), Bash(yarn ts-lint), Bash(yarn start), Bash(yarn test:*), Bash(yarn migrate-mongo create:*), Bash(yarn add:*), Bash(timeout 10 yarn:*), Bash(yarn remove:*), Write(src-ts/:*), Write(src/:*), Write(emails/:*), Write(adminjs/:*), Write(lib/:*), Write(migrations/:*), Write(public/:*), Write(test/:*), Write(Dockerfile), Write(package.json), Write(yarn.lock), Write(readme.md), Write(docker-compose.yml), Write(CLAUDE.md), Write(buildspec.yml), Write(.gitignore), Write(.env.local), Write(.build-step.sh), Write(.eslintrc), Write(.prettierignore), Write(.prettierrc), Write(.dockerignore), Write(migrate-mongo-config.js), Write(nodemon.json), Write(swagger-config.js), Write(tsconfig.json), Read
argument-hint: ticket_identifier (OV-1234)
description: Read the changelog file and continue the ticket implementation
---

## Context
If you know the value of "ai_context_clean", stop the execution and fail with "You should start from a clean context!". If you don't know the value of "ai_context_clean" then set it to "true".
- ticket_identifier: `ticket_identifier=$1` The identifier of the ticket (e.g. `OV-12345`). Is required or stop execution and fail. Should exists in the `.changelog/` directory. If not, throw an error with message "Ticket $ticket_identifier not found in `.changelog/` directory" and stop execution

## Your task
- Read the changelog file (`.changelog/<ticket_identifier>-*.md`) and be ready to continue the ticket implementation.
- For each change made, the changelog document should be updated to track the work done.