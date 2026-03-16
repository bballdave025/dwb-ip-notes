# IP_Plus_Vision — MorphoGender
## Morphological Cues to Grammatical Gender in French and Russian

**Project:** MorphoGender  
**Status:** Vision + experimental framing  
**Scope:** French and Russian (initially)

---

## What this project is

MorphoGender is a short experimental project that examines how much
grammatical gender can be inferred from **word form alone**, independent of
semantics, context, or usage frequency.

The project treats gender prediction as a **controlled signal-extraction
problem**, not as a language-understanding task.

This project concerns _grammatical gender in natural language_, not human gender or identity.

---

## Core question

To what extent is grammatical gender:

- systematically encoded in orthographic and morphological form, versus
- recoverable only through memorization, lexical semantics, or historical
  knowledge?

This question is evaluated empirically via character-level classifiers and
explicit ablation studies.

---

## Why this is interesting (and non-trivial)

Native speakers often report that grammatical gender is:
- “intuitive,”
- “systematic,” or
- “impossible to explain but obvious.”

This project replaces intuition with **quantified structure**, asking not
*whether* gender can be predicted, but **which cues carry the predictive
signal** and how fragile those cues are under control conditions.

---

## Methodological stance

- Models are intentionally simple (character-level CNNs or RNNs).
- Performance is interpreted *only* in conjunction with ablations.
- High accuracy without robustness is treated as evidence of shallow cues,
  not linguistic insight.

The emphasis is on **explainable failure modes**, not state-of-the-art results.

---

## Key experimental axes

The project systematically varies:

- suffix visibility (masking or removal),
- ending-class balance (e.g., Russian -а / -ь / consonant),
- language (French vs. Russian),
- and model class (suffix-only vs. full character models).

Each variation answers a specific falsifiable question about structure.

---

## Claims (pre-registered intent)

Examples of testable claims include:

- A large fraction of French gender prediction is captured by suffix-level
  regularities.
- Russian gender prediction degrades more sharply under suffix masking than
  French.
- When ending distributions are controlled, remaining accuracy reflects
  deeper morphological patterns rather than simple heuristics.

---

## What this project is not

This project does **not** aim to:
- build a production-quality gender tagger,
- model semantic gender or animacy,
- make claims about cognitive representation in humans,
- or replace grammatical description.

It is a scoped, diagnostic experiment about **form-conditioned regularity**.

---

## Outcome

The intended outcome is a short technical note or portfolio artifact that
demonstrates:
- experimental rigor,
- principled use of ablation,
- and the ability to turn linguistic intuitions into testable structure.

*End of document*
