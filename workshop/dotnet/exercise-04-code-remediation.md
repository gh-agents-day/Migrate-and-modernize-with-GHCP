# Exercise 04 — Code Remediation

**Duration**: 15 minutes
**Copilot Feature**: GitHub Copilot Agent Mode — Automated Code Remediation
**Goal**: Allow Copilot to execute the migration plan and automatically apply all code, dependency, configuration, and build changes.

---

## Background

Code remediation is where the migration actually happens. Once you approve the plan (Exercise 03), GitHub Copilot follows `plan.md` and `progress.md` to make systematic changes across your codebase. It handles four categories of changes simultaneously:

1. **Dependency management**: Updates NuGet packages, removes obsolete references, adds Azure SDK packages
2. **Configuration changes**: Updates `appsettings.json`, connection strings, and environment variables
3. **Code changes**: Replaces source technology APIs with Azure service SDK calls
4. **Build and fix loop**: Compiles the project and automatically resolves any compilation errors

Throughout this process, Copilot runs in Agent Mode and asks your permission at key points before executing tool commands.

---

## Step 1 — Enter `continue` to Start Remediation

In the Copilot chat panel, when satisfied with the plan:

Copy and paste the following prompt into the chat:

```
continue
```

Copilot begins executing the migration following the approved plan.

---

## Step 2 — Approve MCP Knowledge Base Tool Use

Copilot may request access to MCP server knowledge base tools to look up Azure SDK documentation and migration patterns.

1. Review what tool Copilot is requesting access to
2. Click **Allow** to grant permission
3. Copilot uses these tools to follow current Azure SDK conventions accurately

---

## Step 3 — Monitor Dependency and Configuration Changes

As Copilot works through the plan, it will:
- Run `dotnet add package` to add Azure SDK NuGet packages
- Update `appsettings.json` and other configuration files
- Rewrite service client initialization code
- Replace source API calls (message brokers, queues, databases) with Azure equivalents

At each stage:
- Click **Continue** to confirm tool use or commands
- Click **Keep** to accept proposed file changes in the editor

> **Tip**: Open `progress.md` at any time to check which tasks are `[x]` completed vs `[ ]` pending.

---

## Step 4 — Let the Build/Fix Loop Resolve Errors

After initial code changes are applied, Copilot builds the project. Compilation errors caused by the migration are automatically diagnosed and fixed.

Copy and paste the following prompt into the chat if you want insight into remaining errors:

```
The project has build errors after the migration. List the current compilation
errors, explain why each occurred as part of the migration, and propose the
exact code fix for each.
```

Continue clicking **Continue** until the project compiles successfully.

---

## Verify

- [ ] `continue` was entered to start remediation
- [ ] MCP tool permissions were granted when requested
- [ ] New Azure SDK NuGet packages appear in the project file
- [ ] Configuration files (`appsettings.json`) were updated with Azure service settings
- [ ] Project builds successfully (no compilation errors)
- [ ] `progress.md` shows all tasks as `[x]` completed

---

## Key Takeaway

> Copilot's automated code remediation handles the full migration stack — dependencies, configuration, code, and build — without requiring you to write a single line of migration code yourself.

---

**Next**: [Exercise 05 — Validation and Summary](exercise-05-validation-and-summary.md)
