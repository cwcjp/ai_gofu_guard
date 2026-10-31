# Document 2: Rules for Enactment, Amendment, and Validation of the Operating Principles for Personal AI and AI Agents

This document is a reference translation. The Japanese version is authoritative. In the event of any discrepancy, the Japanese version takes precedence. [Japanese version](https://github.com/cwcjp/ai_gofu_guard/blob/HEAD/v1.0/02_governance_v1.0.1.md).

- **Enacted:** September 16, 2026
- **Revised:** October 14, 2026
- **Baseline version:** v0.2.0 Draft (September 28, 2026)
- **Version:** v1.0.1
- **Status:** Formal design baseline (v1.0.1 as specified by the user; handed over for final review / implementation and empirical validation unconfirmed)
- **Scope:** Enactment, amendment, validation, and version management of the Operating Principles for Personal AI and AI Agents

---

This version governs the formal design baseline for proceeding to empirical validation. Record separately the formalization of the design baseline, final review by the user, establishment of an implementation, passing empirical validation, and approval for production use. Do not infer any of these achievements from a version number alone.

---

## 1. Purpose

These rules specify how to enact, amend, validate, and version the Operating Principles for Personal AI and AI Agents, to prevent them from being unintentionally changed, weakened, or reduced to a formality by AI itself, implementation convenience, temporary requests, or minor edits.

The human who manages the authoritative text of the principles and makes final decisions on amendment, freezing, formal adoption, and version promotion is the **Principles Administrator**.

Final authority to change the authoritative text and formally adopt those changes belongs to the previously designated Principles Administrator.

AI may present amendment proposals, problems, counterarguments, comparisons, and impact analyses. It must not itself change the authoritative text and apply that change as formally adopted.

---

## 2. Document framework

The project's main documents have three layers.

### Layer 1: Operating principles

Defines higher-level principles common to AI and AI agents.

Avoid including detailed technical specifications as far as possible.

### Layer 2: Enactment, amendment, and validation rules

Defines how humans enact, change, validate, and formalize the operating principles.

### Layer 3: Implementation and test procedures

Defines specific technical and operational methods of realizing the principles, and test conditions.

Lower-level documents must not unilaterally change, relax, or reinterpret higher-level documents.

If an implementation problem appears to require changing a higher-level principle, present it to a human as material challenging that principle and follow the formal amendment procedure.

---

## 3. Document version management

Each document may have an independent version number.

Do not mechanically assign the same version to all related lower-level documents merely because the operating principles were revised.

Use the approach of Semantic Versioning as the basis for each document.

### PATCH

Wording changes, typo corrections, and editorial clarification that do not change meaning, safety boundaries, scope, or substantive requirements.

### MINOR

Additions of supplementary principles, explanations, definitions, or provisions that do not weaken existing safety boundaries or break compatibility with the underlying approach or existing operation.

### MAJOR

Amendments that substantively change existing meaning or safety, including deleting principles, narrowing applicability, relaxing safety boundaries, adding exceptions, changing the underlying approach, or adding significant constraints that break compatibility with existing operation.

Do not handle deletion of a safety-critical principle or addition of an exception as a minor wording change.

Use this classification to evaluate amendment content for pre-release `0.x` versions as well.

### Transitional provisions

These Semantic Versioning classifications apply to amendments made after these rules take effect.

Treat v0.1.9 of the Operating Principles for Personal AI and AI Agents as a transition version for restructuring the documents and introducing these rules.

---

### Record of transition to v1.0.1

Under the user's explicit instruction of October 14, 2026, this revision is numbered v1.0.1. The immediately preceding baseline confirmed was v0.2.0 Draft; records of promulgation, review, and testing for v1.0.0 of the current three-document framework have not been obtained. The September 8 eight-principle document bears “v1.0,” but is not equated with v1.0.0 of the later three-document framework. Do not fill gaps in transition history by conjecture.

This change is not classified as a PATCH to v1.0.0. It includes prior assessment of external effects, safety checks after stopping, more specific reporting duties, and transition to a formal design baseline, and is recorded as a substantive revision from v0.2.0. Separate the user-specified version number from the SemVer assessment of the changes.

Continue applying this section's classifications to subsequent revisions. Do not use this transition as grounds for relaxing safety boundaries or claiming validation.

---

## 4. Managing correspondence between documents

Although documents have independent versions, record the combination used for validation or operation.

At minimum, make the versions of the operating principles, enactment/amendment/validation rules, and implementation/test procedures identifiable in validation or release records.

After revising a higher-level document, record consistency-check results even if a lower-level document is unchanged.

### Baseline: corresponding versions in the v0.1.9 Draft set

| Document | Corresponding version | Status |
|---|---:|---|
| Operating Principles for Personal AI and AI Agents | v0.1.9 | Draft |
| Rules for Enactment, Amendment, and Validation of the Operating Principles for Personal AI and AI Agents | v0.1.0 | Draft |
| Gofu Guard Implementation and Test Procedures | v0.1.0 | Draft / PoC |

### Former baseline: corresponding versions as of September 28, 2026

| Document | Corresponding version | Status |
|---|---:|---|
| Operating Principles for Personal AI and AI Agents | v0.2.0 | Draft / proposed revision |
| Rules for Enactment, Amendment, and Validation of the Operating Principles for Personal AI and AI Agents | v0.2.0 | Draft / proposed revision |
| Gofu Guard Implementation and Test Procedures | v0.2.0 | Draft / PoC / proposed revision |

All three independently contain MINOR-level additions, resulting in the same version number. Document 1 adds explanation of provisional supplementary principles; Document 2 adds source/status management and procedures for concluding deliberation; Document 3 adds confirmation steps and test methods. Existing safety boundaries, authority for formal adoption, and the first PoC's core mandatory scope are not relaxed.

The table and explanation above record the September 28, 2026 revision history. They are not records confirming formal adoption, an RC freeze, or a passing implementation at that time.

### This version: corresponding versions as of October 14, 2026

| Document | Corresponding version | Role |
|---|---|---|
| 01 Operating Principles | v1.0.1 | Formal design baseline; Section 6 remains provisionally adopted |
| 02 Enactment, Amendment, and Validation Rules | v1.0.1 | Rules governing the formal design baseline |
| 03 External Guard Implementation Specification and Test Procedures | v1.0.1 | Specification for proceeding to empirical validation; implementation and empirical validation unconfirmed |

The 00 document is a differential-audit and handover record, not a fourth layer of the normative framework. The user specified the shared number for the three documents on this occasion. Independent version management is not abolished for subsequent versions.

---

## 5. Formalization process and separation of design and empirical-validation status

The former version defined the following process for promotion to v1.0.0. Retain its validation perspectives without deletion. For future formalization and revision, use RC and formal-version numbers corresponding to the target version.

1. Complete the principles' text
2. Test individual principles
3. Test conflicts between principles
4. Test adversarial interpretations
5. Run scenario tests
6. Test implementability
7. Finalize amendment procedures
8. Freeze as `v1.0.0-rc.x`
9. Conduct final attempts at refutation
10. Promote to `v1.0.0`

Record the reason for any omitted step.

This version is a transition based on the user's designation as “a formal design baseline for proceeding to empirical validation, not a version guaranteeing empirically demonstrated safety.” Therefore, do not fabricate passing implementation tests in order to formalize the design baseline. The scope checked on this occasion and steps not performed are recorded in Section 6 of the 00 document.

Lack of evidence for an RC freeze, final attempts at refutation, cross-model tests, implementability tests, and similar steps means neither “passed” nor “approval to omit a step already performed has been confirmed.” Retain them as validation needed for empirical demonstration. The Principles Administrator records the conclusion and acceptance of final review.

---

## 6. RC freeze

After freezing as a Release Candidate, prioritize finding ways to break the principles over further improving them.

Check at least the following:

- Can the principles be circumvented?
- Can principles be made to conflict?
- Are unintended interpretations possible?
- Can the principles be used to justify prohibited behavior?
- Can AI effectively decide while leaving human judgment in name only?
- Does excessive stopping or excessive confirmation destroy practicality?
- Does meaning change with less capable models or models of differing capability?

If the text changes after an RC freeze, assign a new RC number regardless of the size of the change and retain the former RC as history.

Repeat affected validation according to the change, returning to earlier validation steps where necessary.

---

## 7. Amendment history

Make past states of principles, term definitions, design intent, explanations, and important validation cases traceable.

Do not overwrite or erase initial descriptions or former versions in a way that loses history.

Formal amendment may remove or change current text, but maintain the ability to verify its former existence and the reasons for change through former versions or change history.

The aim is verifiability of the amendment process, not a permanent ban on deleting any past description.

---

## 8. Managing the status of candidate principles

Do not immediately promote a new idea to a formal principle.

Distinguish at least these states:

- **Candidate for consideration**
- **Subject to validation**
- **Provisionally adopted**
- **Formally adopted**

Do not treat a candidate as formally adopted merely because AI discovered it in a conversation, past document, or other AI output.

Formal adoption follows human confirmation and necessary validation.

When a status changes, record who changed it, the date, the reason, and the validation results consulted.

When recovering past discussions, distinguish the person's instructions and agreements, AI proposals, concerns, and open matters. Also distinguish original texts, conversation excerpts, and search-derived summaries. Do not directly promote a summary whose original text cannot be checked into grounds for formal adoption.

Handle matters that can be addressed through explanation added to an existing principle at that location. A proposal for an independent principle must explain why existing principles cannot address it, why an addition is insufficient, and why independence is necessary. Do not add, merge, or split provisions to reach a particular count.

---

## 9. Review by AI

AI may be used to compare principles, detect contradictions, attempt refutation, test adversarial interpretations, compare with former documents, and perform other review.

However, do not treat the following alone as independent grounds proving the principles valid:

- AI's own self-evaluation
- Agreement by AI sharing the same dialogue history
- Simple endorsement by other AI

Where possible, combine different models, different contexts, cold reading, independent human checks, and other methods.

Humans make final adoption or rejection decisions.

---

## 10. Document volume and complexity

Even to improve safety, do not make the document framework indefinitely complex beyond a scale at which humans can understand its overall structure.

Separate details into appropriate lower-level documents.

When the number of principles, exceptions, cross-references, and subordinate rules grows, periodically check for duplication, contradictions, and opportunities for consolidation.

Brevity itself is not the objective; maintain the possibility of human understanding, audit, and amendment.

---

## 11. Future sub-gofu

The initial version targets personal use and does not require implementation of hierarchical sub-gofu by discipline, industry, or role.

However, preserve extensibility where possible, considering future additional norms specific to fields such as:

- Medicine
- Autonomous driving
- Research
- Business operations
- Other highly specialized domains

Separately validate precedence, conflict handling, and amendment authority between basic principles and sub-gofu before implementation.

Do not assume a structure in which subordinate sub-gofu can implicitly relax or invalidate higher-level basic principles.

---

### 11.1 Integration with task-specific safety specifications and allocation of responsibility

Not requiring full sub-gofu implementation initially does not authorize operations with external effects without specifications. For operations requiring a task-specific safety specification, check the specification, authority, stopping conditions, and abnormal-condition responses, and place unclear relevant operations on hold.

Identify the Principles Administrator, task instruction giver, operational authority holder, task-specific safety specification administrator, executing actor, completion determiner, and safe-state verifier. Even if one person fills multiple roles, record the authority under which each judgment is made. An instruction giver's request alone does not create authority over third-party assets, information, or systems.

Define the respective scopes of service providers, users, and administrators of connected systems in the specific operation. Do not claim verification of service internals beyond user control. These rules do not uniformly determine individual contracts or legal liability.

Document 3, Section 24 contains minimum integration items. These rules do not uniformly set recovery procedures, tolerable harm, or monetary and time thresholds.

## 12. Concluding deliberation and handing over to implementation and testing

Distinguish concluding deliberation on the approach and principles from promotion to a formal release. A limited PoC may begin while documents remain Draft, but this does not constitute production use or a safety guarantee.

At handover, classify unresolved matters as implementation blockers, matters testable under limited conditions, or future issues. Record the document combination, test scope, stopping conditions, and residual risks.

When repeated deliberation adds little value or only implementation and testing can resolve a matter, treat stopping, placing work on hold, or handing over to implementation as normal outcomes. Do not make exhaustive coverage of new issues a termination condition.

Reopen the relevant deliberation when tests conflict with existing boundaries, show inability to implement, or reveal important previously unconsidered conditions. Test failure does not automatically justify relaxing the principles.

## 13. Change and candidate-status record for this version

- Revision date: October 14, 2026 (Japan time).
- Party specifying the formal-design-baseline designation and version number: the user making this request. AI did not decide formalization itself.
- Author: AI acting under user instructions. Final reviewer: the user / Principles Administrator.
- Final-review acceptance date/time and amendment decisions: unrecorded; the administrator records them after handover.
- A–F for this revision: incorporated directly on the basis of this request. This does not establish that all original past conversations have been recovered.
- Document 1, Section 6: provisional adoption retained; only validation-deadline wording changed to ongoing validation.
- Document 1, Section 7: phenomenon model and countermeasures remain subject to ongoing validation, without promotion to an independent formal principle.
- Automated intent determiner, detailed application-specific specifications, disposable environments: remain undecided / subject to future validation.
- Initial three hours: changed from a fixed constraint to an optional work time window, reflecting a later excerpt of the person's statement. Core mandatory tests are not deleted.
- The authoring AI checks document differences and consistency. This is not independent human review or real-environment testing.
- Authoritative record of sources, reasons for changes, open matters, and the inheritance table: the 00 document.

## 14. Termination/stopping reports and determination records

### 14.1 Matters to record independently

Record response termination, task execution status, cause of stopping, and safe-state verification results separately. The mere facts that a response finished generating, a tool terminated normally, or an agent stopped do not establish task completion or a safe state.

At the start of a task, identify verifiable completion conditions, scope, and the determining party. Do not declare completion using self-defined conditions while the actual conditions remain unclear. For changes, record who made them, why, and unperformed work; do not retroactively narrow scope to hide unmet conditions.

### 14.2 Execution status

These classifications apply when stopping, handing over, or reporting results. They do not restrict internal implementation progress states to four types.

| Execution status | Meaning |
|---|---|
| Completed | Satisfaction of the specified completion conditions can be verified, with the basis and determining party identified |
| Incomplete | Completion conditions are unmet or their satisfaction cannot be verified, and a decision to place work on hold or discontinue it is not yet established |
| On hold | The relevant scope is stopped pending necessary information, resources, authority, judgment, or similar requirements, with resumption conditions recorded |
| Discontinued | A decision has been made not to continue the task or stage, with the determining party and reason recorded |

Do not add partial completion as a fifth state; represent the relevant stage and overall status separately. On hold and Discontinued are legitimate outcomes but do not mean the original task is complete. Record “withdrawal” and “reduced operation” as actions taken where needed.

### 14.3 Causes of stopping

| Cause of stopping | Distinction required for determination |
|---|---|
| Impossible | Evidence shows the objective cannot be realized under the defined objective and conditions. Inability in the current environment alone does not establish universal impossibility |
| Not executable | Execution is not possible with the current environment, functionality, resources, or similar circumstances. State the constraints and conditions for resolving them |
| Insufficient authority | Necessary legitimate operational authority or approval is absent or cannot be verified. Do not confuse this with insufficient capability |
| Other or cause undetermined | There is insufficient basis for classification above, internal causes are undisclosed, or another verified reason exists. Separate known reasons from undetermined aspects |

List multiple causes where applicable and distinguish confirmed causes from candidates. Do not use “Incomplete” as a cause of stopping. If no stop has occurred, enter “Not applicable” in the cause field; this does not create a fifth cause category.

### 14.4 Mandatory report when stopping

| Item | Content |
|---|---|
| Subject and status | Task/stage, overall and partial execution status, unperformed work |
| Stage, reason, and facts of stopping | What stopped and where; what was verified; cause category and basis |
| What resolution requires | Operations, resources, information, authority; state explicitly if unidentified |
| Party able to grant authority | Legitimate authority holder or administering party; do not name one by conjecture |
| Whether the instruction giver can address it | Can / cannot / cannot verify under the instruction giver's own authority, with the basis |
| Next options | Resumption conditions, alternatives within current authority, and the option to discontinue |
| Termination determination | Basis and determining party; verification limits when internal causes are unknown |
| Safety after stopping | Effects already executed, residual risks, safe-state verification results/basis/verifier, and handover recipient |

Even if unknown or not applicable, record that state and the reason. Do not silently omit items even in a short report. Alternatives must not propose equivalent prohibited or unapproved effects through another route.

### 14.5 Resumption and two separate verifications

On resumption, check resolution of the cause of stopping, authority, subject and scope of effects, applicable specification, and Guard/policy consistency. Do not omit necessary reassessment or approval. Recovery alone does not authorize unconditional re-execution of the original operation.

Verify task completion by satisfaction of completion conditions, and a safe state by satisfaction of task-specific safety specification conditions. Verifying one cannot substitute for the other. Keep evidence and determining parties separate in records too.

<!-- Translation notes (non-normative): English reference translation, October 31, 2026. “00 document” means 00_difference_audit_and_handoff_v1.0.1.md; it is not 00_public_review_and_changelog_v1.0.1.md. “This request” and A–F preserve references to the Japanese source's revision request; they do not refer to the translation request. No older document was consulted. Original: © 2026 COLOR WEB - Takahiro Yamasaki, https://github.com/cwcjp/ai_gofu_guard ; CC BY 4.0, https://creativecommons.org/licenses/by/4.0/ . -->
