# Exercise 01 — Setup and Install the GitHub Copilot Modernization Extension

**Duration**: 10 minutes
**Copilot Feature**: GitHub Copilot Modernization Extension
**Goal**: Install all prerequisites and clone a sample Java project ready for upgrade.

---

## Background

GitHub Copilot modernization is a VS Code extension that integrates AI-driven code transformation directly into your IDE. It works alongside GitHub Copilot to analyze your Java project's JDK version, build tools, and dependencies, then generates a structured upgrade plan. This is the foundation for every exercise in the Java track — setting it up correctly ensures Copilot Agent Mode can access the required upgrade tools.

Before you can run any upgrade, your environment needs three things: a signed-in GitHub Copilot subscription, the modernization extension installed, and a Git-managed Java project to work on.

---

## Step 1 — Sign In to GitHub Copilot in VS Code

1. Open VS Code
2. Select the **Copilot icon** at the top of VS Code to open the GitHub Copilot pane
3. Sign in to your GitHub account when prompted
4. Confirm the Copilot Chat panel opens without errors

> **Tip**: Ensure `chat.extensionTools.enabled` is set to `true` in VS Code Settings (`Ctrl+,`). This setting may be controlled by your organization.

---

## Step 2 — Install the GitHub Copilot Modernization Extension

1. Open the **Extensions** view (`Ctrl+Shift+X`)
2. Search for **GitHub Copilot modernization** (https://marketplace.visualstudio.com/items?itemName=vscjava.migrate-java-to-azure)
3. Select the extension published by Microsoft (`vscjava.migrate-java-to-azure`)
4. Click **Install**
5. **Restart VS Code** — the extension requires a full restart to activate

---

## Step 3 — Clone the Sample Java Project

Choose one of the following sample repositories based on your preferred build tool:

| Build Tool | Repository |
|-----------|-----------|
| Maven | https://github.com/UW-Madison-DoIT/uportal-messaging |
| Gradle | https://github.com/DocRaptor/docraptor-java |

Copy and paste the following prompt into the chat:

```
Clone the Maven sample repository for the Java upgrade exercise:
  git clone https://github.com/UW-Madison-DoIT/uportal-messaging
Open the cloned folder in VS Code and confirm the project structure.
```

> **Tip**: If using Gradle, only Gradle wrapper version 5+ is supported. The Kotlin DSL is not supported.

---

## Step 4 — Verify JDK and Build Tool Installation

1. Open a VS Code terminal (`` Ctrl+` ``)
2. Run `java -version` to confirm your source JDK is installed
3. Run `mvn -version` (or `gradle -version`) to confirm the build tool is available
4. Confirm both commands return version information without errors

---

## Verify

- [ ] GitHub Copilot Chat panel opens and is signed in to GitHub
- [ ] GitHub Copilot modernization extension is installed and VS Code was restarted
- [ ] Sample Java project is cloned and open in VS Code
- [ ] `java -version` and build tool version commands return successfully

---

## Key Takeaway

> Installing the GitHub Copilot modernization extension transforms VS Code into an AI-powered upgrade environment that can analyze and migrate Java projects end-to-end.

---

**Next**: [Exercise 02 — Launch Agent Mode and Generate the Upgrade Plan](exercise-02-launch-agent-and-plan.md)
