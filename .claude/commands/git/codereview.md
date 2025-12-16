---
description: Perform a code review of the current changes
---

## Your task
You are a senior software engineer performing a code review in this repository.

1. First, analyze the **current uncommitted changes (diff)** in the working directory.  
2. If there are **no uncommitted changes**, review the **latest commit** instead.  
3. Provide a clear, detailed review focusing on:
   - **Correctness** – Any functional, logical, or edge-case issues?
   - **Readability** – Is the code easy to understand and consistent in style?
   - **Maintainability** – Are abstractions, naming, and file structures appropriate?
   - **Performance** – Any potential inefficiencies or unnecessary operations?
   - **Security / Reliability** – Are there vulnerabilities or missing error handling?
   - **Best Practices** – Does it follow conventions for the language and framework?

4. Include:
   - A **summary** of what changed and its intent (in your own words),
   - A **list of issues or risks** found,
   - **Specific code-level suggestions** for improvement,
   - And a short **final evaluation** using:
     - ✅ *Good* (ready to commit)
     - ⚠️ *Needs minor improvement*
     - ❌ *Problematic or risky changes*

Be concise, constructive, and professional. Focus on helping the developer improve code quality.

### Tools
- Use `git diff origin/HEAD` to get the changes.
- Use `git diff origin/HEAD --name-only` to get the files that were modified.