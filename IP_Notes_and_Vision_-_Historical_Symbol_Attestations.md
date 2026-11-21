# IP Notes and Vision — Historical Symbol Attestations

**Project:** Historical Symbol Attestations (HSA)  
**Working nickname:** “Unicode OED” (informal analogy only)  
**Author:** David Black (DWB; GitHub @bballdave025)  
**Date:** 2026-11-09  
**Status:** Independent research vision / potential portfolio project; no implementation commitment  
**Classification:** Primarily A — Independent Research; potential B/C/D/E components as distinguished below  
**Relationship:** Adjacent to historical document analysis, paleography, manuscript studies, and computer vision. **Separate from RMFB's current publication scope.**

---

## 0. What this document is (and is not)

This is a working record of the origin, intellectual-property context, research questions, examples, interpretive limitations, and possible first experiment for a project provisionally called **Historical Symbol Attestations**.

The motivating analogy is the *Oxford English Dictionary* (OED) practice of collecting dated usage evidence and sometimes discovering an example earlier than a previously documented one. Here, the possible objects of study are **graphic forms and their uses** across languages, scripts, manuscripts, printed editions, and writing traditions, including marks without distinct Unicode code points.

The working nickname “Unicode OED” is descriptive, not a claim of affiliation with either Unicode, Inc. or Oxford University Press. The public project name should remain independent of those organizations' marks.

This document is **not**:
- an assertion that any particular symbol was invented on the date of its earliest known example;
- a claim that visual similarity proves shared meaning, transmission, or descent;
- a proposal to automate authoritative paleographic, philological, or historical conclusions;
- a commitment to a particular generative model, watermark, search corpus, publication, or collaboration;
- a request to expand or slow the present *Reused Manuscript Fragments in Bindings* (RMFB) publication work.

**Working rule:** “earliest *located* attestation” is an evidence-status label, not an invention date or claim of historical priority.

---

## 1. Origin and motivation

The idea arose from curiosity about the histories of familiar signs, including Mac keyboard symbols (particularly the place-of-interest / Command sign `⌘`) and their possible older uses. A conversation with Gemini during an earlier period of exploratory research helped focus the question: could computational visual search identify *earlier located examples* of symbols or symbol-like forms than existing catalogues currently report?

Historical manuscripts, post-1066 documents, early printed editions, monetary notation, and marginal attention marks have supplied additional observations and research leads. The chronology among the Mac-symbol discussion and the author's investigation of Nordic mark notation is not presently reconstructed.

The initial goal is a **credible, bounded portfolio exercise**: document a small set of genuine examples, test a retrieval idea, expose the limits, and learn from expert review. A larger historical research program is a possible later development, not a prerequisite.

A symbol without an established name or Unicode encoding can still be assigned an internal identifier, described, imaged, compared, and investigated.

---

## 2. Core distinctions and evidentiary posture

The project must distinguish at least the following:

1. **Graphic resemblance:** Two shapes appear similar. This is a search lead, not proof of common identity.
2. **Function or meaning:** Two signs serve comparable purposes, such as “look here,” textual correction, ownership, or monetary accounting. Shared function does not establish historical descent.
3. **Demonstrated relationship:** Documentary, paleographic, textual, chronological, or other specialist evidence supports a historical connection or transformation.
4. **Encoding identity:** A Unicode character or sequence is a modern representational convention. It is not itself an attestation or a faithful image of every historical glyph variant.
5. **Document and edition:** An original manuscript's date, a later copy's date, a first printed edition's date, and a modern editor's typeset rendering must be recorded separately.
6. **Object and hypothesis:** A specific observed mark is evidence of its own presence. Assigning it to a named family or function may remain tentative.

A *symbol family*, an *individual graphic variant*, a *specific occurrence*, and a *claim about that occurrence* should be separately identifiable.

Use provenance-aware language: “located in,” “appears to resemble,” “potentially served,” “tentatively grouped with,” and “relationship not yet established.” Preserve conflicting or negative identifications rather than silently overwriting them.

---

## 3. Candidate families and branches

This is a **discovery menu**, not a claim that all entries are related or that all deserve new code points.

### 3.1 Attention, editorial, and textual navigation

- Manicules / pointing hands, including divergent orientations and forms.
- *Nota bene* signs and NB monograms; multiple variants already observed by the author, with images and source information to be supplied.
- Eye-like marks that may indicate something like “look here!”; actual functions undetermined pending source review.
- Pilcrows, section signs (including the “silcrow” naming question), asterisks and asterisms, daggers, quotation marks, diples, correction signs, and editorial symbols.
- Parentheses, brackets, and other punctuation or textual delimitation forms.

### 3.2 Monetary, commercial, and accounting notation

- Percent, per mille, currency signs, dollar signs, historic pound signs and pound-weight signs, hash / number sign, commercial at, and other quantity/weight notation.
- Nordic and other *mark* forms; mark/markke notation (see §4).
- Proposals to investigate connections among `lb`, `℔`, `£`, and `#`, **without assuming** any particular genealogy.
- Ownership symbols, account-book marks, household bookkeeping conventions, merchants' marks, and livestock brands.

### 3.3 Scribal, mathematical, musical, and specialized symbols

- Scribal abbreviations and ligatures, including the history of `&` from Latin *et* as a useful example of a historically documented relationship.
- Earlier and later forms of Hindu-Arabic numerals.
- Musical notation, astronomical and alchemical signs.
- Historical ritual marks or sigils in grimoires, which may be individualized rather than shared characters.
- Heart-shaped marks and related motifs, where graphic resemblance, decoration, and semantic use must be distinguished.

**Boundary:** Scribal abbreviation systems could become a substantial branch of their own. They are included as research leads and possible ancestors of particular signs, not an immediate commitment to survey them comprehensively.

---

## 4. Motivating case: Nordic mark notation (not a manicule)

A particularly instructive case emerged during an investigation of symbols in post-1066 historical documents and their printed editions. The author recalls **at least two especially interesting variants**: a simpler, more triangular printed form and a still simpler, few-stroke form in the earlier-document trail. Exact specimens, dates, and relationships remain to be re-established. **Do not collapse these observations into one proven continuous lineage.**

### 4.1 Known encoding and source leads

- `₻` — **U+20BB NORDIC MARK SIGN**. It is distinct from `₰` — **U+20B0 GERMAN PENNY SIGN**, which initially proved a red herring.
- Unicode proposal: [Proposal to add Nordic Mark Sign, L2/12-242](https://www.unicode.org/L2/L2012/12242-mark-sign.pdf). The proposal includes printed Holberg-related examples and notes a different handwritten sign associated with a 1721 letter. The quoted 1926 editorial representation is not automatically the handwritten mark itself.
- [Aboensis font documentation](https://ctan.math.washington.edu/tex-archive/fonts/aboensis/aboensis.pdf), especially **§6.1, Mark/markke**, is a promising reference for medieval Scandinavian notation and scribal abbreviations. A delightful illustration in that document features **a fox preaching to geese** (not sheep); the illustration is an adjacent manuscript-art interest, not a project requirement.
- [MUFI character recommendations](https://mufi.info/) and their discussions of historic mark variants offer further leads.
- [Wikipedia: Currency symbol](https://en.wikipedia.org/wiki/Currency_symbol) lists `₻`; the broader currency-symbol catalogue is useful for candidate discovery, not proof of individual historical claims.

The author remembers an **early-twentieth-century reference** found by a circuitous route. It has **not been recovered**. Previously mentioned sources, including a possible 1933 bibliographic lead, must not be represented as that remembered work unless confirmed. There is also an unresolved story about an individual being credited with inventing a sign despite earlier apparent examples; neither the figure nor the claim is presently identified.

### 4.2 Why this case matters

This case offers a concrete demonstration of:
- manuscript versus print versus modern encoding;
- graphic simplification and variant comparison;
- historical accounting context and differing linguistic traditions;
- a search beginning with an unfamiliar **shape**, not merely a known word;
- potential disagreement between editorial normalization and the source image.

**Provisional variant labels** (internal, non-genealogical): `MARK-ENC` (modern encoded reference), `MARK-PRINT-TRI` (recalled triangular print), and `MARK-EARLY-FEW` (recalled simpler form). Labels describe the investigation, not established ancestry.

No first-attestation or inventor claim is made.

---

## 5. Existing observations, hypotheses, and unanswered questions

### 5.1 Observations and leads already in hand

- The author has collected numerous *nota bene* variants, some apparent eye-like attention signs, and source information; the images and attribution records **have not yet been supplied here**.
- The Nordic mark investigation identified `₻`, several historically represented forms, and an unresolved early-twentieth-century bibliographic trail.
- The Mac `⌘` / place-of-interest sign is an origin-story and possible research target. The author does **not** recall encountering a convincing example during extensive RMFB image review.
- A separate personal collection of scribal-abbreviation references exists; Aboensis is an addition to that reading list, not proof that its contents have been exhaustively evaluated.

### 5.2 Hypotheses (not findings)

- Visual retrieval could surface uncatalogued or earlier *located* occurrences of some sign families.
- Synthetic augmentation might help a model retrieve rare historical-looking symbol variants with few labeled examples.
- Functional context (marginal location, adjacent text, accounting columns, document genre) might reduce false positives compared with shape-only retrieval.
- Search could be useful even where there is no Unicode code point, provided visual forms and evidence records are kept independently.

### 5.3 Open questions

- Which marks are characters, glyph variants, ligatures, annotations, logos, motifs, or unique personal signs?
- What counts as an attestation of *form* versus *function* versus a particular historical name?
- What coverage already exists in OED quotations, paleographic manuals, MUFI, Unicode proposals, manuscript catalogues, and specialist scholarship?
- How will dating ranges, uncertain dating, copy chains, editorial substitutions, and provenance be represented?
- What is the minimum crop resolution required, and how should a candidate be reviewed in the context of its whole page?
- How should the project handle image rights, source licenses, and attribution without redistributing restricted photographs?
- How much synthetic realism can be generated responsibly, and what release restrictions are necessary?

---

## 6. Possible workflow: from evidence to reviewable retrieval

A possible sequence, **not yet an implementation plan**:

1. **Register genuine exemplars.** Assign occurrence IDs; record archive/institution, collection, shelfmark or stable URL, image/page/folio, bibliographic reference, date or range, location on page, rights, transcription (where relevant), and uncertainty.
2. **Describe forms independently of Unicode.** Store an internal family hypothesis, local graphic label, Unicode or MUFI cross-reference if useful, geometry, context, and open alternatives. Keep visual similarity separate from historical interpretation.
3. **Create explicitly synthetic training candidates.** Explore controlled transformations, compositing, handwriting-style augmentation, or generative models (possibly GANs or diffusion methods) only after an ethics/release design has been chosen. Log originating exemplars, generation settings, transformations, identifiers, and synthetic status.
4. **Search or rank candidates.** Compare shape or learned image embeddings with genuine digitized materials, optionally using page-layout, text, and archival metadata.
5. **Review in context.** Experts inspect original-page context, paleographic features, documentary dating, editorial history, and alternatives. A model's similarity score is never a scholarly attribution.
6. **Publish cautiously, if at all.** Report verified occurrences, provenance, uncertainty, failure cases, and review process. “Earliest located” must always be scoped to searched materials and search date.

Evaluation must use **separate genuine historical examples**, never synthetic images as purported ground truth for historical attestation. Split by manuscript/source object, edition or related provenance groups as appropriate; avoid near-duplicate leakage. If the available genuine evaluation examples are too few, report a demonstration rather than a generalizable accuracy result.

A minimal record might distinguish `occurrence_id`, `source_id`, `page_or_folio`, `date_range`, `graphic_variant_id`, `family_hypothesis`, `function_hypothesis`, `evidence_status`, `image_rights`, `is_synthetic`, and `review_status`. This is illustrative, not a frozen schema.

---

## 7. Synthetic evidence integrity: mandatory design constraint

**The project may seek visually convincing synthetic “forgeries” for computational training, but it must never allow those images to masquerade as authentic historical evidence.**

A plausible failure mode is a synthetic crop escaping its labeled dataset, appearing on Wikipedia/Wikimedia or elsewhere as a historical specimen, and later being cited or re-ingested as independent evidence. Such contamination would be particularly damaging to an earliest-attestation project.

Before generating or distributing realistic synthetic specimens, define layered safeguards:

- **Manifest-level provenance:** immutable synthetic designation, source and generator references, generation date, model/version/seed where feasible, transformation chain, and stable IDs.
- **Dataset separation:** clearly segregated storage and namespaces; do not mix generated examples into historical exemplar directories; exclude synthetics from claims and historical evaluation.
- **Visible disclosure for presentation:** conspicuous “SYNTHETIC — NOT HISTORICAL EVIDENCE” labels on public demonstrations, recognizing that labels can be cropped.
- **Watermarking and provenance research:** evaluate robust embedded marks, crop-local watermarking, image fingerprinting, and signed provenance metadata/content credentials. No technique is assumed reliable against all cropping, resizing, recompression, or malicious modification.
- **Distribution review:** do not publicly release an unlabeled, convincing synthetic corpus merely because training is complete. Consider withholding high-fidelity outputs while releasing methods, safer examples, manifests, and evaluations.
- **Contamination and failure tests:** verify crop survivability, false detection of genuine images as synthetic, and watermark effects on historically relevant fine strokes. Test transformations especially at *individual-symbol crop* scale.
- **Expert oversight:** synthetic marks may aid retrieval; they may not be cited as historical attestations.

**Research leads only:** [NIST, *Reducing Risks Posed by Synthetic Content*](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-4.pdf); [C2PA specifications](https://spec.c2pa.org/); and research on robust image watermarking (e.g., InvisMark). The author recalls FamilySearch discussions about watermarking that might survive cropping and file-format changes, and associates **Heath Nielsen** and **Pat Schone** with those discussions. This is a personal recollection and **not a verified publication, patent, or technical attribution**; search it later only if useful.

No robust watermark is a substitute for provenance and responsible release.

---

## 8. One bounded pilot (optional, not an immediate assignment)

**Candidate pilot: a small set of genuine *nota bene* and eye-like attention marks supplied by the author.**

Why: they are motivated by existing observations, can support a narrow visual-search test, and force the central distinction between graphic resemblance and an attested “look here” function. Their exact provenance must be provided before the pilot is designed.

**Proposed portfolio-level deliverable:**
- a small provenance-linked exemplar registry;
- a very modest retrieval baseline (for example, hand-designed features or pretrained visual embeddings);
- a ranked candidate-contact-sheet workflow showing whole-page context and abstentions;
- a short error analysis including false lookalikes, source-level split discipline, and ethical handling of any augmentation.

**Success criterion:** a reproducible and interpretable demonstration that returns reviewable genuine candidates—not a novelty claim, an earliest-ever claim, or a production discovery engine.

**Fallback pilot:** the Nordic mark family, *if* enough genuinely sourced and rights-compatible variants become available. Avoid conflating different manuscripts, printed editions, and Unicode exemplars.

**Explicit stopping rule:** finish the project-definition note, retain the open questions, and return attention to the RMFB paper. No broad search, model training, massive corpus download, or new collaboration is required now.

---

## 9. Potential Fort Point Upskilling Collabs project

If pursued after the RMFB publication milestone, a bounded collaboration could assign independent, attributable contributions:
- one participant organizes provenance/rights and source-to-crop links;
- one implements a transparent retrieval baseline with reproducible evaluation;
- one builds a reviewable visualization or annotation workflow;
- the project owner coordinates historical questions, consults specialists, and documents uncertainty.

Names, commitments, participant roles, contribution agreements, access permissions, and publication plans are **not yet decided**. Contributor credit should be tied to actual work (commits, data curation, analysis, scholarly review), not presumed. Source institutions and experts receive proper citation; rights and licensing are checked before any distribution.

Specialist review is integral if the project makes historical claims. Computational similarity alone is insufficient; the system is intended to **help experts find and evaluate evidence**, not to replace them.

---

## 10. IP classification, separation, and data rights

This document follows [IP_Classification_Framework_rev2026-06-08.md](IP_Classification_Framework_rev2026-06-08.md).

- **A — Independent Research:** historical-attestation questions, hypotheses, critical interpretation, and scholarly framing (primary).
- **B — Personal ML Learning Experiments:** initial synthetic-augmentation and retrieval notebooks, if built.
- **C — Shareable Experiments:** a later bounded collaborator-facing pilot, if agreed.
- **D — Personal General-Purpose Tooling:** independent indexing, record/provenance, or visualization utilities, if built as reusable tools.
- **E — Potentially Integrable Independent Tooling:** only if future independent infrastructure is intentionally designed for adaptation; no such integration is implied today.

Work is intended to be conducted independently, using personal resources and publicly available or appropriately licensed data. Employer-confidential information, internal implementations, restricted collections, and credentials are excluded. Recollections of general workplace conversations do not authorize use of employer material or imply employer endorsement.

**A public GitHub branch is publicly readable.** This document deliberately records the *outline* of personal observations and hypotheses without embedding unpublished original crops, unpublished source inventories, sensitive employment material, or files whose rights are unsettled. “Private notes” here means **not yet approved for broader release or promotion**, not GitHub access control. Review disclosure choices before merging, publishing elsewhere, or sharing images.

Code, metadata, and historical images may require separate licenses or release decisions. Historical public-domain status of a manuscript does not by itself settle reproduction rights for every supplied digital photograph.

---

## 11. Relationship to RMMFB: hard scope boundary

RMFB may later provide candidate images, source links, or technical lessons, **only after** its existing scholarly and publication commitments are protected and applicable rights permit.

HSA does **not**:
- change the RMFB dataset, labels, splits, evaluation plan, or manuscript;
- add symbol detection to RMFB's current paper;
- consume the time allocated to the RMFB publication goal (before the end of 2026);
- create a dependency that RMFB must solve before publication.

The intended outcome of this note is a **parked, well-defined independent idea**. Return to publishing RMFB.

---

## 12. Source leads and deferred bibliography

These are starting points, **not** a completed literature search, nor proof of particular priority claims.

- [Unicode, proposal L2/12-242: Nordic Mark Sign](https://www.unicode.org/L2/L2012/12242-mark-sign.pdf).
- [Aboensis typeface documentation](https://ctan.math.washington.edu/tex-archive/fonts/aboensis/aboensis.pdf), especially §6.1, *Mark/markke*.
- [Medieval Unicode Font Initiative (MUFI)](https://mufi.info/), medieval character recommendations and historical forms.
- [Wikipedia: Currency symbol](https://en.wikipedia.org/wiki/Currency_symbol), discovery index only.
- Evina Steinová, *Most Common Western Annotation Symbols in the Early Middle Ages* (working reference for medieval annotation signs; bibliographic verification later).
- OED historical quotation methods and specialized symbol histories: compare word-name first attestations, graphic-form occurrences, and function-specific uses.
- NIST synthetic-content provenance research; C2PA; crop-resistant watermarking literature (all deferred).
- The author's missing early-twentieth-century monetary-symbol source, the inventor-attribution anecdote, and the full NB/eye-mark provenance records (**unresolved; do not manufacture details**).

---

## 13. Next handoff / review gate

**Before merging or advancing this project**, the author intends to supply:
1. Several examples of *nota bene* variants, with original-source references.
2. Examples of an eye-like mark apparently directing attention to a particular location or passage (“look here!”), again with source attribution.
3. Where possible, original images/crops and enough archive, page, folio, date, and rights information to link each image to its source.

Once those materials are supplied, add the images **only if permitted** and attach explicit provenance and attribution to each. Preserve uncertainty about function. Do not invent missing URLs or bibliographic information.

After this review gate: merge at the author's discretion; **resume RMFB publication work**. All broader HSA implementation, collaboration, and publication decisions remain postponed.

---

## Closing note

The objective is to help recover and document how marks actually appeared and were used, including forms not conveniently expressible in modern character encodings. The ambition is not to manufacture an authoritative history from lookalikes; it is to make genuine evidence easier to locate, scrutinize, and connect—while ensuring that the synthetic examples used to improve search can never be mistaken for historical proof.

*End of document*
