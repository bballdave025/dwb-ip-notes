# IP_Plus_Vision — Ambiguity Corpus
**Project:** Multi-Modal Ambiguity Corpus for Instruction Following and Reasoning  
**Author:** David Black (DWB, GitHub @bballdave025)  
**Status:** Vision and scope document (living)  
**Intended audience:** LLM researchers, applied linguists, ML practitioners, and evaluation teams  
**Sharing intent:** Open methodology; examples are illustrative and independently reproducible

---

## 0. What this is (and what it is not)

This document describes the **vision, scope, and design principles** for an Ambiguity Corpus intended to support:

- instruction-following robustness,
- chain-of-thought (CoT) evaluation,
- multi-modal reasoning,
- and principled handling of underdetermined inputs.

It is **not**:
- a claim of proprietary data,
- a benchmark leaderboard,
- a replacement for task-specific datasets,
- or a claim that ambiguity can or should be eliminated.

The corpus exists to **expose ambiguity deliberately**, not to hide it.

---

## 1. Why ambiguity deserves its own corpus

Most ML systems are trained as if:
- inputs are well-posed,
- instructions are internally consistent,
- and ambiguity is noise.

In real human communication, ambiguity is:
- pervasive,
- structured,
- and often *intentional*.

Failures in instruction following, safety alignment, and reasoning quality frequently arise not from lack of knowledge, but from **misinterpreting ambiguous inputs**.

This project treats ambiguity as a **first-class object of study**, not a nuisance.

---

## 2. Core design principle: ambiguity ≠ error

A central distinction in this corpus is between:

- **errors** (violations of grammar, logic, or intent), and
- **ambiguities** (inputs with multiple plausible interpretations).

The corpus records:
- *why* an item is ambiguous,
- *how* interpretations diverge,
- and *what information would resolve it* (if any).

This framing prevents models from being rewarded for:
- hallucination,
- over-confident disambiguation,
- or implicit bias toward a single reading.

---

## 3. Two parallel tracks: linguistic and material ambiguity

The corpus is intentionally **multi-modal**.

### 3.1 Linguistic ambiguity

Examples include (non-exhaustive):
- homophones and homographs (e.g., *tear*, *bass*),
- scope ambiguity (especially negation),
- hyphenation and compound attachment,
- pronoun reference and missing antecedents,
- coordination ambiguity (“old men and women”),
- register-driven reinterpretation (“It pains me not …”).

These are annotated with:
- possible readings,
- minimal rewrites to disambiguate,
- and short tags for later analysis (LEX, STR, RI-A, etc.).

### 3.2 Material / visual ambiguity

Inspired by manuscript studies and document analysis, this track includes:
- fingerprints (scribe vs later reader),
- pressed plants (keepsake vs specimen),
- marginal doodles,
- erasures and palimpsests,
- offset ink, bleed-through, or wormholes misread as punctuation.

These cases emphasize that **visual ambiguity is not always resolvable from pixels alone**.

---

## 4. Annotation philosophy: evidence vs inference

A strict rule governs inclusion:

> **Annotations describe what is structurally present in the input, not what might plausibly have existed on the original artifact.**

This applies to both text and images.

If defining features are not explicitly resolvable:
- the item is marked ambiguous or indeterminate,
- not “recovered” through contextual guesswork.

This protects against:
- over-annotation,
- model overconfidence,
- and evaluation leakage.

---

## 5. Why this matters for LLM evaluation

Ambiguity stress-tests capabilities that standard benchmarks miss:
- whether a model can recognize underdetermination,
- whether it can ask clarifying questions,
- whether it can maintain multiple hypotheses,
- whether it abstains when appropriate.

These behaviors are **core to safe and reliable deployment**, yet are rarely measured directly.

---

## 6. Intended uses

The Ambiguity Corpus is designed to support:

- instruction-following evaluation,
- CoT prompting and analysis,
- regression tests for prompt changes,
- multi-modal reasoning benchmarks,
- interview and training exercises,
- qualitative probes of model behavior.

It is **not tied to any single architecture**.

---

## 7. Relationship to other work

This project overlaps conceptually with:
- linguistics (scope, pragmatics, discourse),
- manuscript studies (material ambiguity),
- human-factors research,
- and ML evaluation.

It intentionally avoids claiming novelty in isolation; its contribution is **integration and discipline**.

---

## 8. What success looks like

Success is not a single score.

Success looks like:
- better prompts,
- better abstention,
- clearer model explanations,
- fewer silent failures,
- and increased trust in model behavior under uncertainty.

---

## 9. Closing note

Ambiguity is not a bug in human communication.
It is a feature.

Any system meant to operate alongside humans must learn to recognize it, respect it, and respond proportionally.

This corpus exists to make that possible.

---

*End of document*
