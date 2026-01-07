# IP_Plus_Vision — Measuring Instruction Consistency

**Project:** Measuring Instruction Consistency  
**Author:** David Black (DWB)  
**Status:** Vision + problem formalization (working document)  
**Scope:** Task instructions, annotation guidelines, policy constraints, and reward specifications  

---

## 0. What this is (and what it is not)

This document outlines a **research and analysis framework** for identifying, classifying, and measuring **instructional inconsistency** in complex systems.

It is **not**:
- a claim that any specific system is “bad” or “broken,”
- a critique of particular products or organizations,
- a proposal for a single universal metric.

It **is**:
- a formalization of a class of problems that are currently handled informally,
- a bridge between intuitive human judgments (“this makes no sense”) and measurable structure,
- a foundation for future tooling, audits, and research.

---

## 1. Motivation: when “harder is allowed but easier is forbidden”

Across many domains—annotation pipelines, task triage systems, safety policies, and reinforcement learning—users encounter rules that feel *principled locally* but *incoherent globally*.

Canonical examples include:
- trivial mechanical tasks being forbidden while harder semantic tasks are allowed,
- instructions that contradict themselves over the same category,
- policies that restrict future-input comparison but allow deep interpretive judgments,
- reward specifications that imply mutually incompatible outcomes.

These situations are often described as:
> “Inconsistent,” “arbitrary,” or “ridiculous.”

This project exists to replace those reactions with **precise diagnosis**.

---

## 2. Core claim

Instructional failure is not monolithic.

There exist **distinct, structurally different kinds of inconsistency**, including:
- logical contradiction,
- functional non-determinism,
- ontological (type) mismatch,
- policy–capability mismatch,
- non-monotonic permission over task complexity,
- temporal or relational access asymmetry.

Treating all of these as “inconsistency” obscures both cause and remedy.

---

## 3. The unifying abstraction

At its core, an instruction set is meant to define a **function**:

$ f : Inputs → Allowed actions / labels / outcomes $

Failures occur when:
- the function is not well-defined,
- the domain is ill-typed,
- the codomain is internally contradictory,
- or the permission structure violates intuitive partial orders (e.g., difficulty, information access).

This project treats instruction sets as **formal objects** that can be:
- analyzed,
- stress-tested,
- and compared.

---

## 4. A taxonomy of instructional failure modes (high level)

This work distinguishes, at minimum, the following categories:

### 4.1 Direct logical contradiction
Two rules assign incompatible outcomes to the same set of inputs.

Example pattern:
> “All X → A”  
> “All X → B”

This is an **unsatisfiable specification**.

---

### 4.2 Functional non-determinism
Overlapping rules assign different outcomes to partially overlapping subsets.

This produces:
- irreducible ambiguity,
- entropy that cannot be eliminated with more data.

---

### 4.3 Ontological / type errors
Rules reference concepts that do not belong to the declared domain.

These are:
- logically satisfiable,
- but semantically incoherent.

They signal a mismatch between the instruction language and the task universe.

---

### 4.4 Policy–capability mismatch
The system permits tasks that are:
- semantically complex,
- subjective,
- or computationally difficult,

while forbidding tasks that are:
- mechanical,
- deterministic,
- or strictly simpler,

due to unrelated constraints (e.g., temporal access, cross-input comparison).

This is not a contradiction—but it is a **normative inconsistency**.

---

### 4.5 Non-monotonic permission structures
Permission does not increase monotonically with:
- task simplicity,
- information locality,
- or computational tractability.

This violates user expectations and complicates system reasoning.

---

## 5. Why this matters (beyond annoyance)

Instructional inconsistency has concrete downstream effects:

- **Annotation noise** that no model can learn away.
- **Irreducible disagreement** between competent labelers.
- **Reward non-identifiability** in reinforcement learning.
- **Policy confusion** that encourages workaround behavior.
- **Loss of trust**, even when individual rules are defensible.

Critically, many of these failures are **structural**, not implementation bugs.

---

## 6. Measurement, not vibes

A central goal of this project is to move from:
> “This feels inconsistent”

to:
> “This instruction set exhibits *this specific failure mode*, with *this measurable impact*.”

Candidate measurement approaches include:
- conflict rates over defined domains,
- entropy of implied label distributions,
- type coverage metrics,
- disagreement lower bounds,
- and permission monotonicity tests over task embeddings.

The emphasis is on **diagnosis**, not blame.

---

## 7. Relationship to learning systems

These issues are especially acute in:
- supervised learning (label noise vs. specification error),
- reinforcement learning (reward inconsistency, sparse or contradictory signals),
- agentic systems (routing, tool access, and memory constraints).

Many learning failures attributed to “model weakness” are better understood as **instructional impossibility**.

---

## 8. Collaboration and audience

This project is intended to be useful to:
- ML practitioners designing datasets and reward functions,
- researchers studying alignment and safety,
- annotation pipeline designers,
- policy authors,
- and auditors evaluating system behavior.

The aim is not to replace judgment, but to **support it with structure**.

---

## 9. Near-term outputs

Planned near-term artifacts include:
- a refined taxonomy with formal definitions,
- illustrative toy examples mapped to failure classes,
- small, reproducible demonstrations,
- and a short technical or workshop-style paper.

---

## 10. Closing note

Instructional inconsistency is not a moral failing, nor a sign of incompetence.
It is a natural consequence of:
- scale,
- layered design,
- and evolving requirements.

This project exists to make those failures legible—so that systems, and the people who use them, can reason more clearly about what is and is not being asked.

---

*End of document.*
