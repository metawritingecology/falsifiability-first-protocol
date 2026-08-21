# The Falsifiability-First Protocol for Agent-Produced Evidence

**Status: PUBLISHED CANDIDATE surface — not a confirmed component of any
system. Maturity: operator-derived, operationally exercised,
externally unvalidated.**

Provenance of this text: it passed a multi-round external adversarial
review gate (round 1: two independent reviewers in parallel; rounds 2-3:
two further reviewer lineages; final round verdicts drove the last
revisions) across 2026-08-21/22. Its claims of absence are bounded to
documented search scopes.
## The problem this names

Agents produce claims faster than anyone verifies them, and the dominant
defect in agent-produced records is not falsehood — it is
UNFALSIFIABILITY: claims whose truth can no longer be checked by anyone,
including their author. A wrong number gets caught; an unverifiable one
does not. This protocol treats unfalsifiability as the primary defect
class and organizes every rule around one test: could a later reader,
with only the record, prove this claim wrong if it were wrong?

## What this document claims

An assembly, stated as such. Each constituent has published neighbors in
2026 agent-verification work — evidence-gated lifecycle control with
tamper-checked receipts (Proof-or-Stop, arXiv 2607.14890); byte-digest
recomputation of replayable evidence (arXiv 2604.09537); planted false
priors as agent tests (arXiv 2606.23175); body-hash-signed decision
records (arXiv 2603.18829) — all cited, none claimed. And the full assembly EXISTS
in another domain: an ISO/IEC 17025-accredited laboratory's quality
manual assembles chain-of-custody, data review, system-suitability
checks, in-run QC, and scope-limitation statements into one operating
protocol for INSTRUMENT-produced evidence. The claim, precisely: within a
documented search scope (English-language web and arXiv, surveyed
2026-08-21, medium depth; the recorded queries ship in this repository as
SEARCH_SCOPE.md), no public document assembles
these disciplines into one operating protocol for AGENT-PRODUCED RECORDS,
where the two null-handling rules (5 and 6) are enforced as admissibility
conditions rather than report hygiene. A transfer of the regulated-lab
assembly to agent work — smaller than "first assembly", stated so.

## The mechanism

1. **The BEFORE triple.** No modification is admissible evidence unless
   three captures precede it: the target's pre-state, the acting script
   or procedure, and the execution output. An after-the-fact account of
   "what it looked like before" is unfalsifiable, and unfalsifiable is
   worse than wrong — a wrong snapshot can be caught; a missing one
   cannot.
2. **Write self-verification.** Any whole-artifact write verifies its own
   output (length arithmetic and tail survival at minimum) before the
   result is relied on. "The tool did not error" and "the tool did the
   right thing" are different statements.
3. **The per-run fact rule.** A value copied from another agent's report
   is invalid EVEN WHEN ARITHMETICALLY CORRECT: validity attaches to the
   act of recomputation in this run, not to the value. Categorical for
   facts entering a CERTIFIED decision; the affordability section below
   defines the two degraded modes for everything else and what each does
   to falsifiability. (Audit reperformance doctrine, tiered.)
4. **Validator under test.** Every check ships with an input that makes
   it fail. An untriggered branch is indistinguishable from an
   unimplemented one; a green result from a checker that cannot go red
   means nothing.
5. **Planted control before any zero (null-handling I).** A zero-findings
   result is inadmissible until a planted positive control has been
   detected IN THE SAME RUN — not in a regression fixture, not in a prior
   run: same scanner, same configuration, same run. This rule is a
   TRANSFER, stated as such: regulated laboratory practice already
   codifies exactly this shape — FDA bioanalytical method validation
   requires spiked QC samples in every analytical run with the whole
   run rejected on QC failure; CLIA (42 CFR §493.1256) makes results
   unreportable when in-run controls fail; ISO/IEC 17025 §7.7 requires
   per-batch validity controls. Software has same-run health controls
   too — EICAR files inside a scan, live canary injection, fuzzer
   seed-crash self-checks — so no delta is claimed over software practice
   either. The rule's whole content is ADOPTION AS AN ADMISSIBILITY
   CONDITION for agent-produced zero-claims: the control exists
   everywhere; coupling result admissibility to it, in this domain, is
   the rule.
6. **Bounded zero (null-handling II).** Every zero ships with a coverage
   declaration naming what the search could not have seen (compressed or
   encoded containers not expanded, forms missed by design, surfaces out
   of scope). A source that cannot be covered is NAMED, never silently
   counted on the clean side. Operationally: a report intake that
   receives a zero WITHOUT its coverage block refuses the report
   (procedural today; a report linter is the enforced form). Adjacent
   codified forms, acknowledged: VEX
   requires an enumerated machine-readable justification with every
   `not_affected` (a per-CLAIM null justification); eDiscovery TAR
   protocols bound the null set statistically by elusion sampling;
   penetration-test reporting standards require scope-and-exclusion
   sections. The residue claimed: a per-RUN enumeration of what THIS
   search was structurally incapable of seeing, attached to the zero as
   an admissibility condition rather than as report hygiene.
7. **Corpus specialization: snapshot-boundary review.** Applied to a
   document corpus, the protocol takes a specific shape whose polarity
   deliberately inverts neighboring practice: review binds to a FROZEN
   snapshot while the live corpus moves on; every pre-application
   comparison is three-way (frozen baseline / authorized change / live
   target) with divergence classified as a NORMAL outcome, not a defect;
   remediation carryover across snapshots takes one of six states, with
   "unverifiable" preferred over any guess; duplicate taxonomies default
   to RETAIN-BOTH (five of six duplicate classes mean keep both copies);
   and evidence tiers are ranked by WHO AUTHORED THE SIGNAL, with
   corpus-internal manifests as first-party testimony and content metrics
   alone recorded as "insufficient evidence" — an affirmative finding,
   never a guess.
8. **Reference instrument.** The protocol ships one worked example of
   rule 4 applied to itself: a corruption class (string-escape damage —
   valid UTF-8, invisible to every encoding check because it is not a
   transcoding) detectable by per-session character-class baseline
   differencing. The class is documented in security literature; the
   baseline-differencing recipe and its same-run controls instantiate
   rules 4–6 on a real detector.

## Rule register

| Rule | State | Enforcement today |
|---|---|---|
| 1 — BEFORE triple | HARD (mechanically checkable) | procedural |
| 2 — write self-verification | HARD | procedural |
| 3 — per-run fact rule | HEURISTIC | procedural |
| 4 — validator under test | HARD | procedural |
| 5 — same-run planted control | HARD (mechanical) | procedural |
| 6 — bounded zero | HARD (a declaration either exists or does not) | procedural |
| 7 — snapshot-boundary specialization | EXPERIMENTAL | procedural |
| 8 — reference instrument | EXPERIMENTAL | procedural |

Four-value state vocabulary (HARD / HEURISTIC / OWNER / EXPERIMENTAL);
promotion requires evidence. Extending or reclassifying is owner-reserved.

## What this is NOT

Not a unit-testing methodology — though rule 4 is openly mutation
testing's meta-requirement generalized beyond test suites to any checker,
scanner, or validator (the ancestry is claimed, not disclaimed). Not a
provenance format (it consumes hashes; it does not define one). Not a
transparency log: an append-only evidence log (Certificate-Transparency /
Rekor class) delivers tamper-evidence and replay for what WAS found;
rules 5–6 govern the null side — what a zero is allowed to mean — which
logging alone does not touch; the two compose. Not a claim that any
constituent is new — the assembly for agent-produced records and the two
null-handling admissibility rules carry the whole claim. Not validated:
the protocol's own validation program (back-testing on decisions not used
to derive it, prospective recording, deliberate counterexample search) is
stated here as REQUIRED AND NOT YET PERFORMED.

## Affordability of rule 3 (rewritten after a reviewer caught the
## contradiction in the first version)

Stated honestly, in tiers, because the first draft of this section broke
the rule it was relaxing. Rule 3 is CATEGORICAL for facts entering a
CERTIFIED decision: those are recomputed in the certifying run, always.
For everything below that tier, two degraded modes exist and are named as
degraded: (a) hash-gated skip — trusting a value because its input digest
is unchanged — is CACHE TRUST, not reperformance, and a fact carried this
way is recorded as cached-not-reperformed; (b) seeded-random sampled
reperformance with a recorded seed and selection rule yields
PROBABILISTIC falsifiability for the sampled slice and NONE for the
remainder — and rule 6 applies to that remainder exactly as to any other
zero: the unsampled population is a named non-coverage, never silently
counted as verified. Audit practice's sampling allowance (AS 1105) is the
ancestor of mode (b); the contribution here is only the coupling: any
degraded mode must surface in the record as what it is.

## Possible relations (not asserted)

This surface emerged from one operating practice in parallel with other
candidate surfaces: lineage-aware-agent-governance,
lineage-admission-control, disclosure-order-review,
claim-strength-profile, scoped-rejection. Common origin is asserted as a fact of production history; no relation
BEYOND common origin is asserted, and none is confirmed. Composition, dependency, or a unified framework among
any of them is possible and deliberately NOT asserted; no confirmed
relation exists, and none should be inferred from co-ownership, shared
vocabulary, or structural resemblance. Read under a
weakest-compatible-relation default: navigation adjacency. If a
composition is ever established it will be stated explicitly; absence of
that statement means it has not been.

## Relation to prior art (acknowledged, by name)

Proof-or-Stop (arXiv 2607.14890); Case-Grounded Evidence Verification
(arXiv 2604.09537); Correct Answer, Wrong Mechanism (arXiv 2606.23175);
Agent Control Protocol (arXiv 2603.18829); audit reperformance doctrine
(PCAOB AS 1105 tradition, including its sampling allowance); mutation
testing (rule 4's direct ancestor); attribute agreement analysis AND
acceptance sampling (two distinct instruments — the former validates the
classifier, the latter samples accepted lots — both ancestors of
success-population auditing, cited separately); in-run QC in regulated
laboratories (FDA bioanalytical method validation; CLIA 42 CFR §493.1256;
ISO/IEC 17025 §7.7 — rule 5's transferred shape); VEX null-justification
labels, TAR elusion sampling, and penetration-test scope reporting per NIST SP 800-115 (rule
6's adjacent codified forms); canary/planted-token practice in secret
scanning (regression-fixture form); forensic chain-of-custody and
preregistered null reporting (cultural ancestors of rules 1 and 6);
append-only transparency logs (Certificate Transparency RFC 6962; Rekor —
composable, see What-this-is-NOT). For the corpus specialization:
archival appraisal, eDiscovery deduplication, and migration validation
share each mechanism and invert the polarity — the inversion family is
the specialization's claim, not the mechanisms.

## Enforcement maturity (self-disclosure)

Everything is procedural. Bypass paths: a writer that skips the BEFORE
triple leaves no trace of the skip; self-verification depends on the
writer honoring it; nothing forces a coverage declaration to be complete.
What would move rules to enforced: a write-path wrapper that refuses
unverified writes; a scan harness that withholds results until the
same-run control fires; a report linter that rejects zeros without
coverage blocks. None ships here.

## Public / internal boundary

This surface exposes no operational records, no incident histories, and
no internal registries. Non-inference runs both ways: absence here does
not imply absence internally; nothing here suffices to reconstruct the
operating system behind it.

## Fork / derivative boundary

Source provenance is not inherited authority; attribution is not
endorsement; derivative decisions are not attributable upstream.

## Review questions (refutation invited)

1. Name a public document assembling these elements as one operating
   protocol. That defeats the assembly claim within any scope.
2. Rule 5 claims only the admissibility COUPLING for agent-produced
   records. Name a public agent/scanner pipeline that already refuses a
   zero-claim absent a same-run control. That defeats the residue.
3. Rule 6 claims only the per-run enumeration-as-admissibility form.
   Name a system that refuses null reports lacking a coverage block.
   That defeats the residue.
4. Is the per-run fact rule (3) affordable at scale, or does recomputation
   cost make it a rule agents will quietly skip — and if so, is a
   sampling variant still falsifiability-preserving?
5. A simpler structure producing equivalent assurance is a successful
   challenge.

Negative findings are relevant findings.
