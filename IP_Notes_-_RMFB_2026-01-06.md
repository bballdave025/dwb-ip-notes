# IP Notes — RMFB (Reused Manuscript Fragments in Bindings)
Date: 2025-12-29 (living document; updated references 2026-01-06)  
Author: David Black (DWB) — GitHub @bballdave025

## Document map

This repository separates **intellectual-property hygiene** from **vision, narrative, and examples**.

- **This document (`IP_Notes_-_RMFB`)**  
  Defines scope, boundaries, non-claims, and ownership hygiene for the RMFB project.

- **Vision & collaborator-facing narrative**  
  See:  
  [`IP_Plus_Vision_RMFB_rev-2026-01-06.md`](https://github.com/bballdave025/rib-wrist-in-bin-din/blob/main/IP_Plus_Vision_RMFB_rev-2026-01-06.md)

- **Technical experiments, models, and code**  
  Maintained in project-specific repositories (e.g., model tests, notebooks, training harness scaffolds).

This separation is intentional and designed to protect both contributors and future collaborators.

---

## 0. What this is (and what it is not)

RMFB is a **vision-plus-technical direction** document for an open research project
focused on discovering and prioritizing reused manuscript fragments in bindings
and related structural contexts.

It is written to clarify scope, intent, and interpretive boundaries for
collaborators, reviewers, and future readers — not to assert novelty or authority
where neither is appropriate.

RMFB is intended to be **public-domain / open research**, with methods,
documentation, and (where permissible) derived artifacts released openly.

---

### 0.1 Arrival notes (how to read this document)

This document reflects an **iterative arrival**, not a closed theory.

RMFB prioritizes **discovery, preservation, and scholarly access** over
automation-for-its-own-sake. The structure may therefore feel non-linear:
examples may precede formal taxonomy, and uncertainty is surfaced rather than
hidden.

Readers are encouraged to treat this document as:
- a working map rather than a final territory,
- an invitation to collaboration rather than a completed system,
- a record of evolving understanding rather than a teleological argument.

The project is motivated by the recovery of historically meaningful traces while
respecting:
- the labor of past scribes, binders, and conservators,
- the stewardship of modern archives,
- and the interpretive authority of human experts.

---

### 0.2 Explicit non-goals (interpretive guardrails)

The RMFB project explicitly does **not** aim to:

- assert ownership over historical manuscripts, bindings, or images;
- replace expert manuscript scholarship, codicology, conservation, or paleography;
- automate attribution, dating, authorship, provenance, or cultural interpretation;
- infer historical context without expert validation;
- treat machine outputs as authoritative rather than suggestive.

All automated methods are intended as **discovery and triage tools**, not final arbiters.

---

## 1) Project summary

RMFB is a computer-vision–assisted research program to identify **reused manuscript fragments in bindings** (and related “information-bearing writing-surface traces”) across large collections of document images, with the goal of surfacing historically and genealogically valuable material that is currently hard to find at scale.

The basic method is to train and evaluate CV classifiers (and, later, localization/segmentation models) to detect candidate cases and to produce explainability artifacts (e.g., CAM/Grad-CAM style overlays) that support trust and scholarly review.

A key premise: many signals are small, faint, or structurally occluded and can be lost under downsampling; therefore the pipeline must treat resolution/bit-depth constraints as first-order engineering realities (not afterthoughts).

---

## 2) Relationship to FamilySearch and other institutions

This research is personal; it is **not promoted by nor tied to FamilySearch** or any employer.

RMFB’s longer-term vision includes searching large archival and family-history image collections, including (where access and terms allow) genealogical databases, because such searches have not, to the author’s knowledge, been operationalized at scale in these contexts.

---

## 3) What the “thing” is (scope definition)

The target objects are cases where a writing surface (parchment/paper/other) is reused in a binding context—for example:

- pastedowns and flyleaves,
- wrappers and covers,
- spine linings or reinforcements,
- sewn-in guards, tabs, and structural repairs.

**Temporal note.**

RMFB does not assume a single chronological direction of reuse. Writing-surface fragments may predate the bound text (traditional manuscript waste), postdate the original codex due to rebinding or repair, or reflect composite histories in which portions of a codex were previously bound elsewhere before their current assembly. RMFB treats these as distinct but equally valid “information-bearing writing-surface traces,” with temporal interpretation intentionally deferred to domain experts.

Important clarification (to avoid an implicit assumption):
- “Reuse” is not strictly older material binding newer text. **Rebinding and repair can introduce younger material into an older book** (reinforcement, replacement flyleaves, conservation interventions). RMFB treats these as valid “writing-surface traces” when information-bearing.

---

## 4) Prior-art posture and provenance timeline (high-level)

This timeline is for hygiene and orientation—not as a novelty claim.

- 2016–2017: Early concept coalescence (influenced by paleography coursework/MOOCs and fragmentology exposure).
- Late 2017–early 2018: During records-vault digitization work, noticed fragments and binding-context traces (seeded concrete examples and motivation).
- 2023: Primary build-out period for early prototypes, datasets, and conference materials.
- Feb 2024: Public-facing materials include an extended abstract/paper and a talk (Family History Technology Workshop 2024).

(If needed later: add a dated bullet list keyed to commits/releases and dataset snapshots.)

---

## 5) What already exists (artifacts)

### 5.1 Public repos (authoritative pointers)

- `manuscript-waste-reuse-finder` — early paper/talk materials and examples (GitHub).
- `rib-wrist-in-bin-din` — RMFB vision and narrative document + exemplar gallery (GitHub).
- `congenial-chainsaw-rmfb-html` — classification consistency work and example definitions (GitHub).
- `fhtw-paper-code-prep` — reproducible training scaffolds for CV experiments (GitHub).

### 5.2 Model status and claims boundary

- Models discussed or referenced are **exploratory and comparative**.
- No single architecture is claimed as definitive or optimal.
- Abstention, calibration, and human-in-the-loop review are preferred over forced classification.
- Performance metrics are contextual and dataset-dependent.

Any future claims will be supported by documented experiments and explicit uncertainty estimates.

### 5.3 Explainability / trust tooling

RMFB treats explainability artifacts (e.g., Grad-CAM-style overlays and region proposals) as first-class outputs to support adoption by manuscript-studies audiences and to keep the pipeline collaboration-friendly.

### 5.4 Dataset and scale intent (near-term vs. “in-the-wild”)

RMFB is designed to support:
- supervised datasets in the **thousands to tens of thousands** (as labeling capacity permits),
- and “in-the-wild” inference corpora in the **hundreds of thousands** (or more) when access and terms allow.

A practical near-term baseline set exists (e.g., an initial 3331-image set) intended for building repeatable harnesses and testing multi-resolution strategies.

---

## 6) Near-term technical roadmap (clean, reproducible)

1. Lock down a reproducible experimental harness (local → personal AWS if used), including environment capture, deterministic splits, and run logging.
2. Start with a calibrated binary classifier plus abstention, then expand to:
   - multi-label classification aligned with a curated schema,
   - weak localization (“where is the evidence?”),
   - and segmentation/detection once region targets stabilize.
3. Explainability as a first-class artifact: overlays generated automatically per run.
4. Scale-out search: run trained models over large corpora to produce ranked, reviewable candidate packs for scholarly evaluation and follow-up citation.

---

## 7) Publication and collaboration intent

- Target venue: *Fragmentology* (peer-reviewed, open-access), with a staged plan:
  1) a first publication emphasizing search-at-scale, review burden, and discovery rates, and  
  2) a second publication with manuscript-studies collaborators to harden ground truth and codicological interpretation.

I am explicitly comfortable sharing scholarly credit with domain experts to maximize correctness, adoption, and interpretive integrity, provided the work remains openly accessible.

---

## 8) Separation from employer resources (“clean-room” commitments)

To avoid ambiguity about ownership:

- Work is conducted on **personal time**, on **personal hardware/accounts**, and (if cloud is used) via **personal AWS**.
- No employer datasets, credentials, internal tools, or proprietary code are used.
- Training and inference use only data for which I have legitimate access and usage rights under the relevant terms (with attribution/citation norms respected).

---

## 9) Data rights and release strategy (open by default, respectful in practice)

- Code and documentation: released under an OSI-approved license (e.g., Apache-2.0 or MIT).
- Labels / derived metadata: released openly when legally and ethically permissible.
- Images: released only when licensing permits; otherwise publish *pointers* (citations/identifiers) and derived, non-restricted artifacts.

---

## 10) Vision and examples

For motivation, historical context, illustrative examples, taxonomy for the vision doc (A–H), and collaborator-facing narrative, see:

➡️ **IP Plus Vision Document**  
[`IP_Plus_Vision_RMFB_rev-2026-01-06.md`](https://github.com/bballdave025/rib-wrist-in-bin-din/blob/main/IP_Plus_Vision_RMFB_rev-2026-01-06.md)

That document intentionally contains material *not* included here.

---

## 11) “Ask” / why this note exists

This document exists to clearly state:

1) RMFB is a **personal, open-research project** (public-domain intent), and  
2) it is being developed in a way designed to avoid entanglement with employer IP.
