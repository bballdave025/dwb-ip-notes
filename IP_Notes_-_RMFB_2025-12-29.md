# IP Notes — RMFB (Reused Manuscript Fragments in Bindings)
Date: 2025-12-29  
Author: David Black &nbsp;&nbsp;&nbsp;&nbsp; GitHub @bballdave025)  

## 0) One-sentence intent (the thing I most want to protect)
RMFB is intended to be **public-domain / open research**, with methods, documentation, and (where permissible) derived artifacts released openly.

## 1) Project summary
RMFB is a computer-vision–assisted research program to identify **reused manuscript fragments in bindings** (and related “information-bearing writing-surface traces”) across large collections of document images, with the goal of surfacing historically and genealogically valuable material that is currently hard to find at scale. The basic method is to train and evaluate CNN-based classifiers (and later segmentation models) to detect “reuse” cases and then use explainability tooling (e.g., Grad-CAM) to support trust and scholarly review.

## 2) Relationship to FamilySearch and other institutions
This research is personal; it is **not promoted by nor tied to FamilySearch**. 0  
The longer-term vision includes running searches over large archival and family-history image collections, including (where access/terms allow) genealogical databases, because such searches have not, to the authors’ knowledge, been performed at scale in those contexts. 1  

## 3) What the “thing” is (scope definition)
The target objects are cases where a previously used manuscript or writing surface has been detached and reused as binding material (e.g., pastedowns, wrappers, flyleaves). The research writeup describes these as “Reused Manuscript Fragments” (RMF/RMFB) and discusses the broader fragmentology context and relevance. 2  

## 4) Prior art and provenance timeline (high-level)
- 2016–2017: Early concept coalescence (influenced by paleography coursework/MOOCs and exposure to fragmentology ideas).
- Late 2017–early 2018: While working at the Granite Mountain Records Vault, noticed fragments during digitization work (seeded concrete examples and motivation).
- 2023: Primary build-out period for early prototypes, datasets, and conference materials (per your note).
- Feb 2024: Public-facing materials include an extended abstract/paper and a talk (Family History Technology Workshop 2024). 3  

(If needed later, add a dated bullet list keyed to commits/releases and dataset snapshots.)

## 5) What already exists (artifacts)
### 5.1 Public repos (authoritative pointers)
- `manuscript-waste-reuse-finder` — early paper/talk materials and examples (GitHub).
- `rib-wrist-in-bin-din` — expanded methods outline / “funding-friendly” framing (GitHub).
- `congenial-chainsaw-rmfb-html` — classification consistency work and example definitions (GitHub).
- `fhtw-paper-code-prep` (branch: `cifar10-vanilla-cnn`) — reproducible training scaffolds for CV experiments (GitHub).

### 5.2 Research claims already demonstrated (example baseline)
An early approach used transfer learning with **ResNet-50** (ImageNet initialization) and reports strong training accuracy in a small study (“over 600 images…96.77% accuracy…after 30 epochs”). 4  
(This is not a final scientific claim; it is evidence of feasibility and a baseline to improve with stricter evaluation.)

### 5.3 Explainability / trust tooling
The project explicitly targets explainability via Grad-CAM (and related visualization), to support trust and adoption by manuscript-studies audiences. 5  

### 5.4 Dataset and scale intent (near-term vs “in-the-wild”)
A methods draft describes training/validation/test sets on the order of **thousands to tens of thousands** of images, and an inference (“in-the-wild”) set on the order of **hundreds of thousands**. 6  
A planning document also discusses multi-resolution dataset structuring and large-scale folder/pair construction derived from an initial 3331-image set. 7  

## 6) What I plan to do next (near-term technical roadmap)
1. **Lock down a reproducible experimental harness** (local → personal AWS), including environment capture, deterministic splits, and run logging.
2. **Binary classifier first**, then:
   - multi-label classification (your curated label schema), and
   - pixel-level / region-level segmentation for “where the evidence is,” including mixed regions where appropriate.
3. **Explainability as a first-class artifact**: Grad-CAM and related saliency/attribution visualizations generated automatically per run.
4. **Scale-out search**: run trained models over large “in-the-wild” corpora to identify candidate RMFB hits for scholarly review and (where allowed) follow-up citation.

## 7) Publication and collaboration intent
- Target venue: *Fragmentology* (peer-reviewed, open-access), with a staged plan:
  1) a first publication emphasizing scale-of-search and discovery rates in a large “in-the-wild” dataset, and  
  2) a second paper with a manuscript-studies collaborator to harden ground truth and codicological interpretation.
- I am explicitly comfortable sharing scholarly credit with domain experts to maximize adoption and correct interpretation, provided the work remains openly accessible.

## 8) Separation from employer resources / “clean-room” commitments
To avoid any ambiguity about ownership:
- Work is conducted on **personal time**, on **personal hardware/accounts**, and (when cloud is used) via **personal AWS**.
- No employer datasets, credentials, internal tools, or proprietary code are used.
- Any future training/inference uses only data for which I have legitimate access and usage rights under the relevant terms (and will be cited/attributed appropriately in publications).

## 9) Data rights and release strategy (public domain / open)
- Code and documentation: released under an OSI-approved license (e.g., Apache-2.0 or MIT).
- Labels / derived metadata: released openly when legally and ethically permissible.
- Images: released only when licensing permits; otherwise, publish *pointers* (citations/identifiers) and derived, non-restricted artifacts.

## 10) “Ask” / why this note exists
This document exists to clearly state:
1) RMFB is a **personal, open-research project** (public-domain intent), and  
2) it is being developed in a way designed to avoid entanglement with employer IP.
