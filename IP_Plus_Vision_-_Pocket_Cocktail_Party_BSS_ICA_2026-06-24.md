<!-- File: IP_Plus_Vision_-_Pocket_Cocktail_Party_BSS_ICA_2026-06-24.md -->

# IP Plus Vision — Pocket Cocktail Party BSS / ICA

**Filename:** `IP_Plus_Vision_-_Pocket_Cocktail_Party_BSS_ICA_2026-06-24.md`
**Project:** Pocket Cocktail Party
**Repository:** `bballdave025/pocket-cocktail-party`
**Author:** David Black (DWB, GitHub @bballdave025)
**Date:** 2026-06-24
**Status:** Independent portfolio / learning / research-adjacent project

---

## Classification

**Primary Classification:**
B — Personal ML Learning Experiments

**Secondary Classification:**
A — Independent Research

See the 
[IP Classification document](https://github.com/bballdave025/dwb-ip-notes/blob/main/IP_Classification_Framework_rev2026-06-08.md) 
in this repo.

---

## 0. What this is

Pocket Cocktail Party is an independently developed machine-learning and
signal-processing project focused on blind source separation, especially the
classic cocktail party problem.

The project explores how source signals become mixed microphone observations,
how Independent Component Analysis (ICA) and related methods behave under
idealized assumptions, and how those assumptions fail under real-world
recording conditions.

The project is intended as:

* a personal ML learning experiment,
* a portfolio-quality technical project,
* a reproducible signal-processing demonstration,
* and a possible foundation for later independent research into source
  separation failure modes.

The working subtitle is:

> Blind Source Separation through Geometry, Harmonics, and Signal Mixing

---

## 1. What this is not

This project is not:

* employer-assigned work,
* an employer-specific ML pipeline,
* a reproduction of proprietary tooling,
* a use of employer datasets,
* a confidential speech-processing system,
* or an attempt to claim ownership over standard ICA, FastICA, BSS, audio,
  or signal-processing techniques.

It is also not intended to be a commercial audio-production system or a
professional music stem-separation product.

The project intentionally begins with small, interpretable experiments rather
than opaque large-scale models.

---

## 2. Core intuition

The project begins from the standard linear mixing model:

$$
\mathbf{X}(t)=\mathbf{A}\mathbf{S}(t)
$$

where:

* $\mathbf{S}(t)$ is a vector of source signals,
* $\mathbf{A}$ is a mixing matrix,
* and $\mathbf{X}(t)$ is a vector of microphone observations.

Equivalently, each microphone waveform is a weighted sum of the source
waveforms.

For example, if there are $N$ sources and $M$ microphones, then:

$$
\mathbf{S}(t)\in\mathbb{R}^{N},
\qquad
\mathbf{X}(t)\in\mathbb{R}^{M},
\qquad
\mathbf{A}\in\mathbb{R}^{M\times N}.
$$

Which, in Einstein notation, is:

$$
X^m(t)=A^m{}_iS^i(t)
$$

where:

* $S^i(t)$ is source signal $i$,
* $A^m{}_i$ is the mixing coefficient from source $i$ into microphone $m$,
* $X^m(t)$ is microphone observation $m$,
* repeated index $i$ is summed over sources,
* and free index $m$ remains as the microphone index.

This notation is useful because it makes the source-to-microphone relationship
explicit without hiding the dimensional structure.

The main learning goal is not merely to run FastICA.

The more important questions are:

* When does ICA work?
* What assumptions does ICA require?
* How do microphone geometry, source count, noise, echo, motion, and
  underdetermined mixtures affect recovery?
* Why do modern deep-learning approaches become necessary for harder cases
  such as stereo music separation?

The project is therefore about the boundary between clean mathematical
models and messy acoustic reality.

---

## 3. Source-first modeling

A central design principle is source-first modeling.

Synthetic source signals are generated before microphone mixing is applied.
For example, the project may create independent arrays such as:

```text
sound_bass_piano
sound_snare
sound_guitar
sound_violin
sound_voice
```

These are the source coordinates $\mathbf{S}(t)$.

The microphone observations are then generated from those sources using a
geometry-derived mixing matrix:

$$
\mathbf{X}=\mathbf{A}\mathbf{S}
$$

which, in Einstein notation, is:

$$
X^m=A^m{}_iS^i.
$$

This makes the relationship between the mathematical model and the code
explicit.

A microphone near the bass/piano source, for example, may receive a mixture
such as:

```text
mic_bass_piano =
    1.000 * sound_bass_piano
  + 0.200 * sound_violin
  + 0.200 * sound_snare
  + 0.124 * sound_voice
  + 0.124 * sound_guitar
```

The explicit form is pedagogical. The implementation uses matrix operations
where appropriate.

The standard matrix multiplication form is:

$$
\mathbf{P}=\mathbf{A}\mathbf{B}
$$

which, in Einstein notation, is:

$$
P^i{}_j=A^i{}_mB^m{}_j.
$$

Here the repeated index $m$ is summed, while $i$ and $j$ remain as the free
indices of the result.

---

## 4. Synthetic harmonic experiment... plus snare

The first synthetic experiment uses five sources arranged on a regular
pentagon:

1. voice
2. violin
3. guitar
4. bass part played by piano
5. snare-like drum

```text
     voice     guitar


violin             snare

           bass
```

Each source has a corresponding nearby microphone.

The pitched instruments are generated using simple harmonic partials. The
snare is modeled differently, as a transient-heavy noise burst with a short
decay and optional weak C4-centered resonance.

This produces a small but interpretable testbed for ICA.

The goal is to create a system simple enough to understand completely while
still being more meaningful than an arbitrary classroom mixing matrix.

---

## 5. Geometry and the mixing matrix

The project uses geometry to generate mixing coefficients.

For the regular-pentagon setup, adjacent-source bleed and next-nearest-source
bleed are treated differently.

The golden ratio appears naturally because the diagonal-to-side ratio of a
regular pentagon is:

$$
\varphi\approx1.618
$$

If adjacent bleed is set to 0.200, then next-nearest bleed can be modeled as:

$$
0.200 / \varphi \approx 0.124
$$

This gives a simple, explainable mixing structure:

```text
own mic:          1.000
adjacent source:  0.200
next-nearest:     0.124
```

The project may later compare close microphones, center microphones, overhead
microphones, mono collapse, stereo collapse, and reduced-channel scenarios.

---

## 6. Real recording experiment

The project also includes a real-world family recording experiment involving
a simple matching-card game.

This recording is intentionally messy. It includes:

* three microphones,
* multiple speakers,
* environmental noise,
* microphone movement,
* participant movement,
* changing geometry,
* interruptions,
* and non-ideal recording conditions.

These imperfections are not treated merely as nuisances. They are part of the
experimental value.

The real recording allows the project to show how source-separation methods
behave when the assumptions behind the clean synthetic model are violated.

This is especially useful for demonstrating the distinction between:

```text
ICA works under clean assumptions.
```

and:

```text
ICA partially works, fails, or becomes unstable when real acoustic conditions
violate those assumptions.
```

That distinction is central to the project.

---

## 7. Data ethics and consent

The project includes identifiable human voice recordings.

All human recordings used in the public project are collected with consent.
Public redacted consent documentation is maintained in the repository.

Original signed consent forms are retained privately and are not included in
the public repository.

The project is a personal educational and portfolio project, not an
IRB-reviewed academic study. Nevertheless, it intentionally follows basic
responsible-data principles, especially because the recordings include a minor
participant.

The purpose of including consent documentation is to show appropriate
awareness of:

* identifiable voice data,
* family-recorded datasets,
* minor-participant recordings,
* public repository boundaries,
* and responsible ML data handling.

---

## 8. Copyright and musical inspiration boundaries

One synthetic experiment is loosely inspired by Yellowcard-style
instrumentation:

* voice
* violin
* guitar
* bass
* drums

This inspiration is musical and structural, not a claim of affiliation,
endorsement, or ownership.

The project does not use copyrighted Yellowcard audio, recordings, stems, or
scores unless explicit permission is granted.

Any references to Yellowcard are intended as attribution of inspiration and
as documentation of why the instrument set is interesting for a source-
separation experiment.

The project may include a statement such as:

> This project is not affiliated with, endorsed by, or sponsored by Yellowcard.

---

## 9. Relationship to employer resources

To avoid ambiguity about ownership and scope:

* work is conducted on personal time,
* work is conducted using personal systems and accounts,
* the repository is independently maintained,
* no employer datasets are used,
* no employer credentials are used,
* no confidential employer workflows are included,
* no internal tools or task details are reproduced,
* and no proprietary implementation details are incorporated.

The project uses public, standard, widely known concepts from signal
processing and machine learning, including ICA, FastICA, blind source
separation, linear mixing, synthetic signal generation, and basic acoustic
modeling.

These are general technical concepts, not employer-specific information.

---

## 10. Why this belongs under Personal ML Learning Experiments

Pocket Cocktail Party primarily falls under:

> B — Personal ML Learning Experiments

because it is:

* motivated by personal learning,
* designed as a portfolio project,
* based on public ML and signal-processing concepts,
* implemented independently,
* scoped around reproducible technical exploration,
* and not derived from proprietary systems or assigned work.

The project is more than a toy exercise, but its immediate purpose is still
technical growth, portfolio development, and concept exploration.

---

## 11. Why this also touches Independent Research

The project has secondary relevance to:

> A — Independent Research

because it may develop into a more formal analysis of source-separation
failure modes.

Possible research-adjacent directions include:

* controlled comparisons between ideal and real acoustic mixtures,
* microphone-count and source-count effects,
* geometry-change sensitivity,
* AGC and clock-drift effects,
* channel-collapse information loss,
* real-world violations of ICA assumptions,
* and structured documentation of what classical methods fail to recover.

If developed further, the project may support a short technical writeup,
poster, blog post, or independent research note.

At present, however, the primary classification remains personal ML learning
and portfolio experimentation.

---

## 12. Relationship to general tooling projects

Pocket Cocktail Party is distinct from personal tooling projects such as
notebook-generation systems or multimodal logging frameworks.

It may use general tooling, reproducibility helpers, notebooks, or logging
infrastructure, but it is not primarily a general-purpose workflow tool.

Its main object is an ML/signal-processing experiment.

Therefore it is not primarily classified as:

* D — Personal General-Purpose Tooling
* or E — Potentially Integrable Independent Tooling

even though some supporting scripts or documentation patterns may be reusable.

---

## 13. Repository scope

The repository may include:

* synthetic source generators,
* microphone mixing utilities,
* geometric mixing matrices,
* mono and stereo downmix demonstrations,
* ICA/FastICA experiments,
* waveform plots,
* spectrogram plots,
* experiment notes,
* consent documentation,
* development notes,
* and README-level explanations.

The repository should exclude:

* private signed consent forms,
* raw personal files not intended for publication,
* credentials,
* employer materials,
* copyrighted music recordings,
* copyrighted scores,
* and any confidential or restricted data.

---

## 14. Intended development direction

Near-term development goals include:

1. Establish the source-first synthetic pipeline.
2. Generate five interpretable source signals.
3. Build geometry-derived mixing matrices.
4. Run ICA on the clean synthetic mixtures.
5. Add center and overhead microphone configurations.
6. Add mono and stereo collapse demonstrations.
7. Import and inspect the real family-recorded audio.
8. Locate claps and major geometry changes.
9. Run exploratory separation attempts on real data.
10. Document where the assumptions fail.

The intended outcome is not a perfect separator.

The intended outcome is a clear, honest, reproducible project showing:

* what was modeled,
* what was assumed,
* what worked,
* what failed,
* and why the failures are informative.

---

## 15. Portfolio value

The project is intended to demonstrate:

* ML curiosity,
* mathematical modeling,
* signal-processing literacy,
* Python implementation,
* data ethics awareness,
* project documentation,
* reproducibility,
* experimental humility,
* and the ability to connect theory with messy real data.

The strongest portfolio value may come from the contrast between:

* clean synthetic ICA,
* messy real household recordings,
* and deliberately lossy mono/stereo channel collapse.

That contrast shows understanding beyond simply running a library function.

---

## 16. Closing summary

Pocket Cocktail Party is an independently developed personal ML learning
project focused on blind source separation, ICA, source modeling, microphone
geometry, and real-world failure modes.

It is built from public mathematical and signal-processing concepts, personal
synthetic data, and consented personal/family recordings.

It is intended to remain separate from employer systems, employer data, and
confidential workflows.

Its primary classification is:

> B — Personal ML Learning Experiments

with secondary relevance to:

> A — Independent Research

if the failure-mode analysis develops into a more formal research artifact.

The project exists to make the cocktail party problem concrete, reproducible,
messy, interpretable, and portfolio-ready.

---

*End of document*
