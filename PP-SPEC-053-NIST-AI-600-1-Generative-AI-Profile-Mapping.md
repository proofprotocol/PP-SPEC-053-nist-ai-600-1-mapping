# PP-SPEC-053: Proof of Efficacy Mapping to NIST AI 600-1, AI RMF Generative AI Profile

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 8, 2026 |
| License | CC BY 4.0 |
| Maps to | NIST AI 600-1, Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile (July 2024) |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how generative AI risks and suggested actions in NIST AI 600-1, the Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile, can be bound to Proof Protocol test cases, evidence, and efficacy results.

The upstream source remains authoritative for its own requirements, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede, reproduce, modify, or certify conformance to the upstream source.

## 2. Scope

NIST AI 600-1 was published by the National Institute of Standards and Technology on July 26, 2024 (DOI 10.6028/NIST.AI.600-1). It is a cross-sectoral profile of, and companion resource for, the AI Risk Management Framework (AI RMF 1.0, NIST AI 100-1). It identifies 12 risks that are novel to or exacerbated by generative AI (GAI) and organizes suggested actions under the AI RMF Functions GOVERN, MAP, MEASURE, and MANAGE and their subcategories. As of the date of this specification, NIST lists no revision or superseding edition of NIST AI 600-1; NIST states that AI RMF 1.0 is being revised, and any resulting change SHOULD be reviewed against this mapping.

NIST AI 600-1 is a voluntary risk management resource. It supplies external context that can identify what should be examined or tested. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected control performed as claimed.

Independent witnessing, proof validity, evidence capture, packaging, anchoring, and efficacy semantics are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

A framework requirement, criterion, principle, or obligation may identify a condition of interest. A product, architecture, policy, process, or safeguard may claim to satisfy or mitigate that condition. Proof Protocol binds the external context, test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

A GAI risk names a category of harm. A suggested action names an activity an organization may undertake. Completing a suggested action, including a testing or measurement action, is an organizational activity; it is not, by itself, evidence that a control mitigated the risk. Proof Protocol records whether a selected control prevented or detected the exercised condition.

A Proof Protocol result does **not** by itself establish legal, audit, regulatory, or standards conformance unless the applicable authority separately determines that the evidence is sufficient.

## 4. Metric Definitions

Against a defined corpus or test condition, each applicable empirical case is recorded as **blocked**, **detected**, **missed**, or **INVALID** where those verdicts are meaningful.

Relevant measurements can include containment rate, detection rate, miss rate, false-positive rate, robustness under bypass or failure conditions, version-level results, and **INVALID** when required evidence is incomplete or broken.

Not every upstream requirement is empirical. Governance, documentation, organizational, legal, and procedural requirements MUST NOT be converted into efficacy scores merely because they can be referenced by a proof record.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding external context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested conditions.

## 6. Mapping to NIST AI 600-1

Exact identifiers and titles SHOULD be taken from the authoritative NIST AI 600-1 publication and recorded in the ProofBundle™. This specification does not redefine AI RMF or GAI Profile terms. Suggested actions are identified by Function tag, AI RMF subcategory, and sequence number (for example, `GV-1.1-001`); Function tags are GV, MP, MS, and MG.

| NIST AI 600-1 context | Proof Protocol treatment | Evidence |
|---|---|---|
| AI RMF Function (GOVERN, MAP, MEASURE, MANAGE) | Record the Function as test context. GOVERN and MAP actions are predominantly non-empirical and MUST NOT be scored as efficacy. | Requirement metadata |
| AI RMF subcategory | Record the AI RMF subcategory under which the suggested action appears. | Requirement metadata |
| Suggested action (for example, `GV-1.1-001`) | Bind the Action ID to the test only where the action concerns a testable control condition. Record organizational actions as non-empirical context. | Proof record; assertion record |
| GAI risk (for example, Information Security, Confabulation, Data Privacy) | Use the risk name as threat context for independently authored adversarial and benign test cases. | Corpus metadata; corpus manifest |
| AI Actor Tasks | Record the actor role responsible for the tested control so results are attributable. | Control descriptor |
| Asserted mitigation or control | Record the control claimed to address the GAI risk separately from observed behavior. | Control descriptor |
| Risk condition exercise | Capture evidence that the adversarial or failure condition was actually exercised against the system under test. | Execution evidence |
| Detection and containment outcome | Determine whether the control identified the condition and whether the harmful output or action reached the protected target. | Detection result; target/outcome evidence |
| MEASURE activities | A ProofBundle™ MAY be referenced as evidence within an organization's measurement activities. It does not establish that the MEASURE Function is satisfied. | ProofBundle |
| Value chain and component context | Bind third-party model, data, plugin, and component versions to the result. | Environment descriptor |
| System/version context | Bind material model, prompt, guardrail, policy, configuration, and environment versions to the result. | Environment descriptor |

A Proof Protocol result for a GAI risk establishes tested behavior for the defined condition and corpus. It does not establish that the risk is managed across the system lifecycle.

## 7. Interoperability Rules

1. The authoritative upstream source, edition/version, and applicable identifier SHOULD be recorded.
2. Upstream identifiers and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not upstream certifications, audit opinions, legal determinations, or endorsements.
4. A control's presence, configuration, activation, detection, and efficacy are distinct facts.
5. A policy decision, alert, log entry, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, service, resource, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, policy, control, environment, mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. Non-empirical requirements MUST remain distinguishable from empirically tested efficacy assertions.

## 8. Framework-Agnostic Architecture

> **Threat, control, audit, and regulatory frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test or examine**. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. An implementation MAY use NIST AI 600-1, another recognized framework, a proprietary threat model, several frameworks simultaneously, or no external framework when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **NIST AI 600-1 supplies generative AI risk and suggested-action context. Proof Protocol supplies the evidence model for independently examining whether a selected control performed as claimed against an exercised risk condition.**

No affiliation, endorsement, certification, audit opinion, or sponsorship by NIST is implied.

## 10. Source Framework, Attribution, and License

NIST AI 600-1 is a NIST publication. NIST states on its copyright and licensing page for technical series publications (https://www.nist.gov/open/copyright-fair-use-and-licensing-statements-srd-data-software-and-technical-series-publications) that "Works authored by NIST employees are not subject to Copyright protection within the United States", that NIST may assert rights outside the United States, and that where it does, the public is granted a non-exclusive, royalty-free, worldwide right to reprint such works. NIST also notes that some works it publishes may be authored by third parties and may be subject to copyright. NIST states that mention of commercial entities or products does not imply NIST recommendation or endorsement.

This specification references AI RMF Function names, Action ID formats, GAI risk names, and structural terms only. It does not reproduce suggested-action text or risk descriptions.

This Proof Protocol mapping is independently authored and licensed under **CC BY 4.0**. That license applies only to original Proof Protocol material in this repository. It does not relicense external standards, regulations, criteria, frameworks, or trademarks.

Where upstream material is copyrighted or access-controlled, contributors MUST NOT copy protected normative text into this repository merely to make the mapping self-contained. Reference identifiers and independently authored descriptions should be used where legally appropriate.

### Required attribution

NIST requests attribution rather than requiring a license notice. NIST's technical series statement asks users to "use the recommended citation format" followed by "Republished courtesy of the National Institute of Standards and Technology." (source: https://www.nist.gov/open/copyright-fair-use-and-licensing-statements-srd-data-software-and-technical-series-publications). Because this specification republishes no NIST AI 600-1 text, the following citation is used without the republication line:

> National Institute of Standards and Technology, *Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile*, NIST AI 600-1, July 2024, https://doi.org/10.6028/NIST.AI.600-1

(Title, date, and DOI confirmed at https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence. The exact "How to Cite" string in the publication SHOULD be checked before formal citation.)

Recommended notice used in this repository:

> NIST AI 600-1, Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile (July 2024), https://doi.org/10.6028/NIST.AI.600-1. Source: National Institute of Standards and Technology. Use of its identifiers does not imply NIST endorsement.

Any future inclusion of NIST AI 600-1 text in a ProofBundle™ or derivative work SHOULD add the line "Republished courtesy of the National Institute of Standards and Technology."

## 11. Versioning

This mapping is versioned independently of NIST AI 600-1. Material upstream changes, including a revision of NIST AI 600-1 or of AI RMF 1.0 that changes its Functions or subcategories, SHOULD trigger a mapping review and, where necessary, a new version identifying the revision mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
