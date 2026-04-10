# App Modernization with GitHub Copilot — Hands-On Workshop

> **Audience**: Java developers upgrading JDK/Spring Boot, and .NET developers migrating applications to Azure
> **Total Duration**: ~50 min mandatory per track + ~30 min optional exercises per track (see two-track map below)
> **Pre-requisites**: VS Code 1.101+, GitHub Copilot subscription (any plan), Git CLI, JDK (Java track), .NET SDK (.NET track)

---

## What You Will Build

In this workshop you use **GitHub Copilot modernization** — an AI-powered VS Code extension — to complete two real-world modernization scenarios:

- **Java Track**: Upgrade a production Java project from Java 8/11 → Java 21 with Spring Boot 2.7 → 3.2 using Copilot Agent Mode, OpenRewrite, and automated CVE/behavior validation.
- **.NET Track**: Assess and migrate the Contoso University .NET application from on-premises components (SQL Server, RabbitMQ) to Azure services using the `AppModernization-DotNet` custom agent.

You direct Copilot with natural language prompts. Copilot generates all plans, writes all code changes, and validates results. **You never write migration code yourself.**

---

## Prerequisites

- VS Code version 1.101 or later
- GitHub account with active [GitHub Copilot](https://github.com/features/copilot) subscription (Free, Pro, Business, or Enterprise)
- GitHub Copilot modernization extension — installed during Exercise 01 in each track
- **Java track**: Java JDK for both source and target versions, Maven or Gradle
- **.NET track**: .NET SDK installed, ability to build .NET projects locally
- Git CLI for cloning sample repositories
- **Java Copilot CLI track (optional)**: [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli) installed, Node.js 22+, npm 10+
- **Coding Agent exercises (optional)**: Repository admin access, GitHub Copilot Pro, Pro+, Business, or Enterprise plan; .NET 10 SDK for .NET coding agent

---

## Sample Repositories

| Track | Project | Repository |
|-------|---------|-----------|
| Java | Maven — uportal-messaging | https://github.com/UW-Madison-DoIT/uportal-messaging |
| Java | Gradle — docraptor-java | https://github.com/DocRaptor/docraptor-java |
| .NET | Contoso University | https://github.com/Azure-Samples/dotnet-migration-copilot-samples |

> **Java Repo Compatibility**: The Java Copilot CLI and Coding Agent optional exercises work with **any Java project repo** (Maven or Gradle) — not restricted to the samples above. Participants may use the Maven/Gradle samples or their own Java project.

---

## Workshop Map

> **Two-Track Design**: Complete the **Mandatory** exercises first (~50 min per track), then pick any **Optional** exercises based on time and interest. Optional exercises are independent of each other.

---

### 🔵 Java Track — Upgrade Java + Spring Boot

#### Mandatory (~50 minutes)

| # | Exercise | Copilot Feature | Duration |
|---|----------|----------------|----------|
| 01 | [Setup and Install the Extension](./workshop/java/exercise-01-setup-and-install.md) | Copilot Modernization Extension | 10 min |
| 02 | [Launch Agent Mode and Generate the Upgrade Plan](./workshop/java/exercise-02-launch-agent-and-plan.md) | Copilot Agent Mode | 10 min |
| 03 | [Apply Code Changes with OpenRewrite](./workshop/java/exercise-03-apply-code-changes.md) | Agent Mode + OpenRewrite | 15 min |
| 04 | [CVE and Code Behavior Validation](./workshop/java/exercise-04-cve-and-behavior-checks.md) | Security & Consistency Validation | 10 min |
| 05 | [Review the Upgrade Summary](./workshop/java/exercise-05-review-summary.md) | Upgrade Summary Report | 5 min |

#### Optional (~30 minutes — pick any, in any order)

| # | Exercise | Copilot Feature | Duration | Requirement |
|---|----------|----------------|----------|-------------|
| 06 | [Copilot CLI & Custom Agent](./workshop/java/exercise-06-copilot-cli-migration.md) | Copilot CLI + `AppModernization` agent | 15 min | Node.js 22+, npm 10+, Copilot CLI installed |
| 07 | [Coding Agent *(Enterprise)*](./workshop/java/exercise-07-coding-agent.md) | Copilot Cloud Agent | 15 min | Repo admin access, GitHub Copilot Enterprise/Business |
| 08 | [Custom Skill for Sample Project](./workshop/java/exercise-08-custom-skill.md) | Custom Skills VS Code Extension | 15 min | VS Code only (not IntelliJ); open project from Exercise 01 |

---

### 🟢 .NET Track — Migrate .NET to Azure

#### Mandatory (~50 minutes)

| # | Exercise | Copilot Feature | Duration |
|---|----------|----------------|----------|
| 01 | [Setup, Install, and Assess](./workshop/dotnet/exercise-01-setup-and-assess.md) | Assessment + Modernization Extension | 15 min |
| 02 | [Chat-Based Migration with AppModernization-DotNet Agent](./workshop/dotnet/exercise-02-chat-based-migration.md) | AppModernization-DotNet Custom Agent | 10 min |
| 03 | [Plan and Progress Tracker](./workshop/dotnet/exercise-03-plan-and-progress.md) | Migration Plan Review | 10 min |
| 04 | [Code Remediation](./workshop/dotnet/exercise-04-code-remediation.md) | Agent Mode Code Remediation | 15 min |
| 05 | [Validation and Summary](./workshop/dotnet/exercise-05-validation-and-summary.md) | 5-Step Validation Loop | 10 min |

#### Optional (~30 minutes — pick any, in any order)

| # | Exercise | Copilot Feature | Duration | Requirement |
|---|----------|----------------|----------|-------------|
| 06 | [Copilot CLI Migration](./workshop/dotnet/exercise-06-copilot-cli-migration.md) | Copilot CLI + `modernize-azure-dotnet` agent | 15 min | Copilot CLI installed |
| 07 | [Coding Agent *(Enterprise)*](./workshop/dotnet/exercise-07-coding-agent.md) | Copilot Cloud Agent | 15 min | Repo admin access, GitHub Copilot Enterprise/Business, .NET 10 SDK |

---

## Key GitHub Copilot Features Covered

| Feature | Description |
|---------|-------------|
| **Copilot Agent Mode** | Autonomous multi-step execution with tool calls, build loops, and iterative fixes |
| **GitHub Copilot Modernization Extension** | VS Code extension exposing Java and .NET upgrade tools to Copilot |
| **AppModernization-DotNet Custom Agent** | .NET-specific migration agent (uses Claude Sonnet 4.5 by default) |
| **MCP (Model Context Protocol)** | Enables Copilot to access Azure SDK documentation and knowledge bases |
| **Copilot CLI (Java)** | Terminal-based JDK/Spring Boot upgrade using `AppModernization` custom agent (`~/.copilot/agents/appmod-java.agent.md`) — no IDE required |
| **Copilot CLI (.NET)** | Terminal-based .NET migration using `modernize-azure-dotnet` custom agent (`~/.copilot/agents/`) — no IDE required |
| **Copilot Cloud Agent (Java)** | Cloud-native autonomous Java upgrade via GitHub Agents panel — delegates tasks and opens PRs automatically |
| **Copilot Cloud Agent (.NET)** | Cloud-native autonomous .NET migration via GitHub Agents panel with `modernize-azure-dotnet.agent.md` in `.github/agents/` |
| **Custom Skills (Java)** | Project-specific reusable skills stored in `.github/skills/` — encode team migration patterns, apply via Agent Mode, share across the team |

---

## Getting Started

1. Clone or open this repository in VS Code
2. Ensure **GitHub Copilot** and **GitHub Copilot Chat** extensions are installed and signed in
3. Open the Copilot Chat panel (`Ctrl+Alt+I`)
4. Choose your track:
   - **Java** → start with [java/exercise-01-setup-and-install.md](./workshop/java/exercise-01-setup-and-install.md)
   - **.NET** → start with [dotnet/exercise-01-setup-and-assess.md](dotnet/exercise-01-setup-and-assess.md)
5. After completing the mandatory track, pick any optional exercises (06, 07, 08) based on available time

---

## Reference Documentation

| Topic | Link |
|-------|------|
| Java Upgrade Quickstart | https://learn.microsoft.com/en-us/azure/developer/github-copilot-app-modernization/quickstart-upgrade |
| Java Copilot CLI | https://learn.microsoft.com/en-us/azure/developer/java/migration/github-copilot-app-modernization-for-java-copilot-cli |
| Java Custom Agent | https://learn.microsoft.com/en-us/azure/developer/java/migration/migrate-github-copilot-app-modernization-for-java-custom-agent |
| Java Coding Agent | https://learn.microsoft.com/en-us/azure/developer/java/migration/github-copilot-app-modernization-for-java-coding-agent |
| Java Predefined Migration Tasks | https://learn.microsoft.com/en-us/azure/developer/java/migration/migrate-github-copilot-app-modernization-for-java-predefined-tasks |
| Java Custom Skills | https://learn.microsoft.com/en-us/azure/developer/java/migration/migrate-github-copilot-app-modernization-for-java-quickstart-create-and-apply-your-own-task |
| .NET Migration Quickstart (VS Code) | https://learn.microsoft.com/en-us/dotnet/azure/migration/appmod/quickstart |
| .NET Migration via Copilot CLI | https://learn.microsoft.com/en-us/dotnet/azure/migration/appmod/copilot-cli-support?toc=/azure/developer/github-copilot-app-modernization/toc.json |
| .NET Coding Agent | https://learn.microsoft.com/en-us/dotnet/azure/migration/appmod/coding-agent-support |
| .NET Predefined Migration Tasks | https://learn.microsoft.com/en-us/dotnet/azure/migration/appmod/predefined-tasks |
| Copilot CLI documentation | https://docs.github.com/en/copilot/how-tos/copilot-cli/use-copilot-cli-agents/overview |
| About Copilot Cloud Agent | https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent |
| Copilot Modernization FAQ | https://learn.microsoft.com/en-us/dotnet/core/porting/github-copilot-app-modernization/faq |
| Generate Unit Tests (Java) | https://learn.microsoft.com/en-us/azure/developer/github-copilot-app-modernization/quickstart-unit-tests |

---

> **Instructor Note**: Exercises are designed so participants never write migration code — they copy **prompts** and let Copilot generate all outputs. Allow extra time for build/fix loops in Java Exercise 03 and .NET Exercise 04, as duration depends on project size and build speed.
