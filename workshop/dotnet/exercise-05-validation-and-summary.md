# Exercise 05 — Validation and Summary

**Duration**: 10 minutes
**Copilot Feature**: GitHub Copilot Modernization — 5-Step Validation Loop and Migration Summary
**Goal**: Complete the automated 5-step validation loop to confirm the migration is secure, functionally correct, and complete, then review and accept the final summary.

---

## Background

A successful build after code remediation (Exercise 04) is necessary but not sufficient for a production-ready migration. GitHub Copilot modernization for .NET runs a comprehensive **5-step validation and fix loop** that goes beyond compilation:

1. **CVE detection**: Identifies known vulnerabilities in updated NuGet packages and auto-fixes them
2. **Build verification**: Re-runs the build and resolves any remaining compilation errors
3. **Functional consistency**: Analyzes code for behavioral changes that could affect runtime correctness
4. **Unit test validation**: Runs existing tests, detects failures, and auto-generates fixes until tests pass
5. **Migration completeness**: Scans for migration items missed in the initial code pass and addresses them

Each step runs automatically — your role is to approve Copilot's actions using **Continue** and **Keep**.

---

## Step 1 — Let the Validation Loop Run

After code remediation completes, Copilot automatically begins the validation loop. Follow each prompt:

| Prompt You Will See | Your Action |
|---------------------|-------------|
| "Detecting CVEs in current dependencies" | Click **Continue** |
| "Building project and resolving errors" | Click **Continue** |
| "Analyzing code for functional consistency" | Click **Continue** |
| "Running unit tests and fixing failures" | Click **Continue** |
| "Checking for missed migration items" | Click **Continue** |

> **Tip**: If asked to approve individual file changes, review the diff in VS Code before clicking **Keep**.

---

## Step 2 — Review CVE Remediation Findings

When the CVE step completes, review what was found. For any CVE not automatically fixed:

Copy and paste the following prompt into the chat:

```
List all CVEs detected in this .NET migration that were not automatically fixed.
For each, provide the CVE ID, affected package, severity level, and recommended
manual remediation steps.
```

---

## Step 3 — Confirm Unit Tests Pass

After the unit test validation step:

1. Open the VS Code **Testing** panel (the beaker icon in the Activity Bar)
2. Confirm all previously passing tests still pass
3. If Copilot auto-generated fixes for failing tests, review the changes before accepting

---

## Step 4 — Review the Migration Summary and Accept Changes

After all validation steps complete, Copilot generates a final summary in the chat window.

Copy and paste the following prompt to get a structured summary:

```
Generate a concise migration summary for this .NET migration, including:
what Azure services replaced which on-premises components, total files changed,
CVEs fixed, unit test results, and any recommended follow-up actions.
```

When satisfied with all changes, click **Keep** to finalize and accept the migration.

---

## Verify

- [ ] All 5 validation steps completed without critical errors
- [ ] All critical/high-severity CVEs were detected and resolved
- [ ] Project builds successfully after full validation
- [ ] Unit tests pass or known failures are documented and understood
- [ ] All migration changes were reviewed and accepted with **Keep**

---

## Key Takeaways

> The 5-step validation loop is what separates a "code that compiles" migration from a "production-ready" migration — Copilot automatically checks security, correctness, test coverage, and completeness.

---

<!-- Instructor Guide: Allow extra 5-10 min if the project has unit tests, as the test fix loop can take time. Encourage participants to explore the diff in VS Code Source Control to see the full scope of changes made. -->

> **.NET mandatory track complete.** Continue to the optional exercises:

**Next (Optional)**: [Exercise 06 — Migrate .NET to Azure Using Copilot CLI](exercise-06-copilot-cli-migration.md)

Or explore:
- [Predefined Tasks for .NET Migration](https://learn.microsoft.com/en-us/dotnet/azure/migration/appmod/predefined-tasks)
- [GitHub Copilot Modernization FAQ](https://learn.microsoft.com/en-us/dotnet/core/porting/github-copilot-app-modernization/faq)
