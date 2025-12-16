---
allowed-tools: atlassian, Bash(git add:*), Bash(git commit:*), Bash(git status:*), Bash(git checkout:*), Bash(git push:*), Bash(grep:*), Bash(find:*), Bash(cat:*), Read
description: Commit & Push the current changes
---

## Context
- Ticket number: From Current branch get the OV-X prefix where X is a number. If you can't find the prefix throw an error and stop execution

## Your task
Commit the changes. On the commit message add a title starting with the ticket number. Summarize the changes using bullets. Do not mention Claude, Claude Code, or Anthropic in the commit message. Push the changes to the remote branch
