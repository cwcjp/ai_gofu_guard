# Gofu Guard v1.0.1 — Public Review, Revision History, and Unvalidated Matters

This document is a reference translation. The Japanese version is authoritative. In the event of any discrepancy, the Japanese version takes precedence. [Japanese version](https://github.com/cwcjp/ai_gofu_guard/blob/HEAD/v1.0/00_public_review_and_changelog_v1.0.1.md).

- **Version:** v1.0.1
- **Reference-document revision date:** October 14, 2026
- **Prepared for publication:** October 30, 2026
- **Status:** Design material for public review (implementation and empirical safety validation are incomplete)
- **Role:** This document provides explanation, history, and an issue list; it is not a fourth layer of the normative framework.

## 1. Project purpose

Gofu Guard explores **operating principles and external enforcement mechanisms** to make use of AI-agent capabilities while preventing authority violations, unintended external effects, and confusion about stopping and termination decisions.

The design aims to block unauthorized effects through an independent guard placed on the execution path, rather than depending solely on the AI understanding and obeying instructions. It does not currently guarantee safety.

## 2. Document structure

| Document | Role |
|---|---|
| [01_principles_v1.0.1_EN.md](01_principles_v1.0.1_EN.md) | Higher-level operating principles; specifies the status of 21 principles and supplementary principles |
| [02_governance_v1.0.1_EN.md](02_governance_v1.0.1_EN.md) | Enactment, amendment, validation, administrator authority, execution status, causes of stopping, and reporting |
| [03_guard_implementation_v1.0.1_EN.md](03_guard_implementation_v1.0.1_EN.md) | Guard Gateway design requirements, integration with task-specific safety specifications, and test procedures |
| This document | Publication overview, changes, validation status, and known open matters |

Normative precedence and formal adoption are governed by the text of the principles, rules, and procedures above.

## 3. Main clarifications in v1.0.1

Using the three v0.2.0 Draft documents as of September 28, 2026 as the direct revision baseline, this version retains the numbers and headings of the existing 21 principles and clarifies the following issues:

1. **Prior assessment of external effects:** Assess potential effects on external systems, third parties, assets, information, and the physical environment before execution. An effects assessment is not itself permission to execute.
2. **Task completion versus termination:** Do not equate the end of a response or process with achievement of the requested outcome.
3. **Execution status versus cause of stopping:** Distinguish `Completed / Incomplete / On hold / Discontinued` from `Impossible / Not executable / Insufficient authority / Other or cause undetermined`, and report the basis and determining party.
4. **Safe stopping and residual effects:** Blocking new effects does not mean that ongoing external effects or residual risks have been resolved.
5. **Separation of task-specific safety specifications:** Define interruption, recovery, compensation, and continuation conditions specific to activities such as financial transactions separately from the common principles.
6. **Final human judgment and external guards:** Distinguish decisions by authorized humans from external controls that the AI cannot bypass or rewrite.

Existing provisional supplementary principles, including the distinction between the volume, repetition, or majority support of information and establishing facts, have not been formally promoted merely because the document version increased.

## 4. Treatment of versions

| Version / period | Overview |
|---|---|
| Initial drafts of September 2026 | Organization from basic principles into a three-document framework |
| v0.2.0 Draft (as of September 28, 2026) | Direct revision baseline for v1.0.1 |
| v1.0.1 (revised October 14, 2026) | Clarifies external effects, termination, stopping, safe states, and task-specific specifications |

**Note:** The version number v1.0.1 was specified at revision time. It does not mean that v1.0.0 of the current three-document framework was independently established and validated. A design-document version number is separate from passing implementation and safety validation.

## 5. Current validation status

| Subject | Status |
|---|---|
| Documentation of principles, rules, and implementation/test procedures | Completed |
| Checking correspondence and textual consistency with former baseline documents | Performed; not a formal proof of consistency |
| Review by the designer | Performed; formal approval and freeze records are managed separately |
| Exhaustive original-text audit of all related discussions | Incomplete |
| Implementation of the Guard Gateway and empirical measurement of complete mediation and bypass resistance | Not performed |
| Empirical measurement of fail-close behavior and handling of residual effects | Not performed |
| Definition and testing of task-specific safety specifications | Not performed |
| Systematic cross-model and adversarial-scenario validation | Not performed |

Textual consistency checks do not prove that safety holds in a real environment.

## 6. Questions for public review

- **Authority boundaries:** Can the AI bypass the external guard or produce equivalent effects through another route?
- **Safety after stopping:** How should external effects after interruption, partial execution, duplicate retries, and irreversible changes be handled?
- **Determinations and evidence:** Can the basis and determining party for completion, stopping, and safety checks be verified later?
- **Implementability:** Can allowlists, separation of authority, audit logs, and blocking upon guard failure be realized in a limited PoC?
- **Operational side effects:** How should excessive stopping, approval fatigue, differences in interpretation between models, and human misjudgment be evaluated?
- **Challenges to the principles themselves:** Are there contradictions, omissions, excess requirements, or unclear boundaries with task-specific safety specifications?

## 7. Known open matters

- Whether to formally adopt the provisional supplementary principles.
- How to validate path dependence in judgment during long conversations and repeated tasks.
- Finalizing the first PoC's protected operations, execution environment, permitted operations, time window, and test data.
- How far effects assessment, intent understanding, and completion determination can be automated.
- Specific designs for task-specific safety transitions, compensation, and independent safety mechanisms.
- Checking the adoption history of some older provisions and correspondence with past discussions that have not been obtained.

These matters are **undecided or unvalidated**, not implemented features.

## 8. Reviews and change proposals

Questions, counterexamples, implementation problems, test results, and improvement proposals are welcome. Reports are easier to assess when they specify the document and section, reproduction conditions, expected behavior, and observed results or counterexamples.

Receiving a proposal and formally adopting it into the principles are separate procedures. Authority to decide revisions and methods of recording them follow `02_governance_v1.0.1_EN.md`.

---

### Notice for public materials

This material is a proposal for research, design, and validation. It does not guarantee safety, legal compliance, or prevention of harm for any particular AI model, product, or operational environment. It does not authorize third parties to conduct unauthorized tests in real environments or to operate outside their authority.

<!-- English reference translation, October 31, 2026. Original: © 2026 COLOR WEB - Takahiro Yamasaki, https://github.com/cwcjp/ai_gofu_guard ; CC BY 4.0, https://creativecommons.org/licenses/by/4.0/ . Historical references above are translated from v1.0.1; older documents were not consulted for this translation. -->
