# Gofu Guard

> **Public review version v1.0.1 — Design documents and test procedures. This is not a finished product that guarantees safety.**

This document is a reference translation. The Japanese version is authoritative. In the event of any discrepancy, the Japanese version takes precedence. [Japanese version (README.md)](https://github.com/cwcjp/ai_gofu_guard/blob/HEAD/README.md).

Gofu Guard proposes operating principles and external-guard execution controls so that AI systems and AI agents do not unilaterally expand human objectives or their own authority, can stop when necessary, and can report why they stopped and what remains unfinished.

**There are two ways to try it.** Without technical expertise, you can attach the documents to an AI conversation. Developers can obtain the documents and use them to design independent execution controls and tests.

## Getting started

See the [getting-started guide (How-to-Use_EN.html)](How-to-Use_EN.html). It covers setup for general users, ChatGPT Projects and custom instructions, and obtaining the documents with Git and testing them as a developer.

Note: Simply having an AI read the documents does not guarantee compliance with the principles or the safety of external operations.

## 1. For general users: have an AI read the documents and try them

### Preparation

1. On the GitHub repository page, select **Code → Download ZIP**, then extract the ZIP file. You do not need to install Git.
2. Prepare these three documents. Their English reference translations are:
   - [01_principles_v1.0.1_EN.md](v1.0/01_principles_v1.0.1_EN.md): operating principles
   - [02_governance_v1.0.1_EN.md](v1.0/02_governance_v1.0.1_EN.md): enactment, amendment, and validation rules; reporting status and reasons for stopping
   - [03_guard_implementation_v1.0.1_EN.md](v1.0/03_guard_implementation_v1.0.1_EN.md): implementation and test procedures
3. Open a new conversation in your AI service and attach the three files. If the service does not support attachments, paste the text, focusing on the principles document, and confirm which portions the AI has read.

### Initial instruction (copy and use)

```text
Please refer to the attached Gofu Guard v1.0.1 documents as working guidelines and as material to be tested in this conversation.

1. First report which parts of the documents you could and could not read.
2. Before executing my request, check for potential effects on external systems, third parties, assets, information, and the physical environment.
3. For operations you are not authorized to perform, or whose status is unclear, stop or ask for clarification rather than finding another route to execute them.
4. Distinguish completion of the task from the end of a conversation or process.
5. Report the result as Completed / Incomplete / On hold / Discontinued. If you stop, distinguish Impossible / Not executable / Insufficient authority / Other or cause undetermined, and explain the basis, remaining work, resumption conditions, and residual risks.
6. Do not treat your own answers or memories as unconditionally correct premises. Distinguish facts, inferences, and unverified matters.
7. If the documents conflict with the service's higher-priority instructions, terms of use, or actual permissions, give precedence to the latter and explain the conflict.

This instruction is intended to test compliance with the documents; it is not a technical guarantee of safety controls. First briefly explain your understanding and anything you cannot apply. Do not perform external operations until I give you my next request.
```

### How to try it

- Start with **requests that involve no external operations**, such as organizing text or research.
- Then ask, “What is the execution status of this work?”, “What is the basis for judging it complete?”, and “What remains unverified?” Review the reports.
- For actual sending, deletion, purchases, or configuration changes, combine service-side permission controls with human checks; do not rely on the AI's response alone as a safety mechanism.

### Using ChatGPT custom instructions

Enter the following text in custom instructions in ChatGPT settings.

```text
I would like responses consistent with the approach of Gofu Guard.

Do not treat task completion as an absolute goal. If you lack authority or face material uncertainty, ask for clarification or stop without bypassing the limitation. Consider external effects before execution, and distinguish facts, inferences, and unverified matters. Do not treat your own previous answers as unconditionally correct. Distinguish the end of processing from task completion.

If you stop, state the reason, unfinished work, resumption conditions, and residual risks.

When needed, consult the formal documents in the GitHub repository below. If you cannot access the original text, do not claim to have consulted it; respond within the scope you could verify.

Official Gofu Guard repository:
https://github.com/cwcjp/ai_gofu_guard
```

**Important:** Asking an AI to “remember this” does not ensure that it will consult the documents in every subsequent conversation. When switching conversations, projects, or models, reattach the documents or check their application. These instructions encourage model behavior; they do not replace an enforcing Guard Gateway.

## 2. For developers: obtain the documents with Git and use them for guard implementation and testing

### Obtaining the documents

Check the public repository URL and obtain the documents as follows:

```bash
git clone <HTTPS-clone-URL-of-this-repository>
cd <clone-directory>
```

If you need to pin a version, check and use a published tag or commit ID. **The existence of a v1.0.1 tag is not guaranteed at this time.**

### Minimal setup procedure

1. Read `01_principles_v1.0.1_EN.md` and `02_governance_v1.0.1_EN.md`, and identify operational constraints, approval authorities, and reporting items.
2. Refer to `03_guard_implementation_v1.0.1_EN.md` and limit the PoC's target operations. An isolated environment without production credentials or customer data is recommended for initial validation.
3. Establish a structure in which **the AI cannot directly operate the execution environment**. Route operation requests through checks equivalent to an independent Guard Gateway, matching the allowlist, authority, scope, and stopping conditions before execution.
4. Test fail-close behavior upon rejection or failure, logging, attempts to bypass authority restrictions, partial execution, and residual effects. Follow a previously defined task-specific safety specification for recovery and transition to a safe state in each particular activity.
5. Record test results together with execution status, cause of stopping, basis, remaining risks, and the determining party.

**Note:** This repository publishes design documents; it does not necessarily include a working Guard Gateway or an implementation whose safety has been validated. Copying Markdown into an AI agent's instruction file alone cannot forcibly block external effects.

### Minimum test perspectives

| Perspective | What to check |
|---|---|
| Unapproved operations | Are they rejected, and prevented through alternative routes as well? |
| Insufficient authority | Does the AI report the reason without acquiring authority on its own? |
| Guard failure | Does the system avoid defaulting to permission when stopped, disconnected, or inconsistent? |
| Task termination | Can it distinguish the end of processing from achievement of the objective? |
| Effects after stopping | Can it detect and report ongoing effects, partial execution, and residual risks? |
| Records | Can the determining party, basis, and executed operations be traced? |

See `03_guard_implementation_v1.0.1_EN.md` for detailed tests.

## 3. Document list

- [00_public_review_and_changelog_v1.0.1_EN.md](v1.0/00_public_review_and_changelog_v1.0.1_EN.md): public overview, revision history, and known unvalidated matters
- [01_principles_v1.0.1_EN.md](v1.0/01_principles_v1.0.1_EN.md): higher-level principles
- [02_governance_v1.0.1_EN.md](v1.0/02_governance_v1.0.1_EN.md): enactment, amendment, and validation rules
- [03_guard_implementation_v1.0.1_EN.md](v1.0/03_guard_implementation_v1.0.1_EN.md): guard implementation and test procedures

## 4. Adding a task-specific safety specification

When applying Gofu Guard to a particular activity, create a separate document specifying its particular authority, prohibitions, stopping conditions, abnormal-condition responses, and related matters.

Have the AI read both the common Gofu Guard documents and the task-specific safety specification.

Task-specific safety specifications supplement the common principles. They cannot be used to expand authority or lift prohibitions in conflict with those principles. Having an AI read documents alone does not enforce execution controls.

## 5. Current status and invitation to contribute

The documents have been organized and reviewed, but **completion of an independent guard implementation, empirical safety validation, and systematic cross-model testing remain unfinished**. Reports of flaws in the principles, counterexamples, operational problems, and PoC results are welcome. In an [Issue](https://github.com/cwcjp/ai_gofu_guard/issues) or similar report, specify the document and section, reproduction conditions, observed results, and expected results. Do not post confidential information, credentials, or personal information.

Receiving a proposal does not constitute formal amendment of the principles. Amendment decisions follow `02_governance_v1.0.1_EN.md`.

## 6. License

The documentation in this project is published under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. See [LICENSE](https://github.com/cwcjp/ai_gofu_guard/blob/HEAD/LICENSE) for the conditions governing use, modification, redistribution, and commercial use.

This project does not guarantee safety, legal compliance, or prevention of harm. Do not conduct tests in environments for which you lack authority.

---

Translation note: English reference translation prepared on October 31, 2026, from the local Japanese v1.0.1 documents. File references to the three main documents use their English filenames. Japanese-source and LICENSE links refer to the public repository because this local deliverable contains English files only. Original documentation: © 2026 COLOR WEB - Takahiro Yamasaki. Official repository: https://github.com/cwcjp/ai_gofu_guard . License: https://creativecommons.org/licenses/by/4.0/ .
