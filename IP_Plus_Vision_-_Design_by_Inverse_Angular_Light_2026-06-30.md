<!-- File: IP_Plus_Vision_-_Design_by_Inverse_Angular_Light_2026-06-30.md -->

# IP Plus Vision — Design by Inverse Angular Light (DIAL)

**Filename:** `IP_Plus_Vision_-_Design_by_Inverse_Angular_Light_2026-06-30.md`
**Project:** Design by Inverse Angular Light (DIAL)
**Author:** David Black (DWB, GitHub @bballdave025)
**Date:** 2026-06-30
**Status:** Independent portfolio / learning / research-adjacent project

---

## Classification

**Primary Classification:** B — Personal ML Learning Experiments

**Potential Future Classification:** C — Shareable Experiments

**Possible Long-Term Classification:** A — Independent Research

See the IP Classification Framework in this repository.

---

## 0. What this is

Design by Inverse Angular Light (DIAL) is an independently developed machine-learning and computational-geometry project exploring how a physical object can be learned from desired optical projections.

The motivating application is a passive digital sundial inspired by existing 3D-printed optical sundials. The broader vision is to explore learned passive optical structures whose projected shadows vary in useful ways under changing illumination.

This project is intended as:

- a personal ML learning experiment,
- a portfolio-quality geometry and optimization project,
- an educational demonstration of differentiable optimization,
- and a possible foundation for later independent research.

---

## 1. What this is not

This project is not employer-assigned work, a proprietary optical-design system, or a claim of inventing differentiable rendering or inverse design. It intentionally builds upon public concepts from machine learning, optimization, computational geometry, ray tracing, inverse design, and passive optics.

---

## 2. Core intuition

Instead of asking:

> What shadow does this object produce?

the project asks:

> What object produces this desired family of shadows?

Machine learning provides a natural framework for searching that design space.

---

## 3. Conceptual formulation

```
desired shadows
      ↓
optimization
      ↓
physical geometry
```

For a learned object M:

```
sun angle θ
    ↓
render(M, θ)
    ↓
predicted shadow
    ↓
loss
    ↓
update M
```

The learned quantity is the object itself.

---

## 4. Candidate object representations

Possible parameterizations include:

- voxel opacity fields,
- layered opacity masks,
- geometric primitives,
- printable wall structures,
- hybrid representations.

A central educational goal is comparing these approaches in terms of optimization behavior, interpretability, manufacturability, and computational cost<sup>[2]</sup>.

---

## 5. Optimization philosophy

Early experiments use continuous opacity values rather than purely binary materials. This produces smooth gradients that make optimization practical. Once optimization converges, the representation can be thresholded or converted into manufacturable geometry.

---

## 6. Experiment 0 — Deep Shadow Learners (DSL)

The first implementation is intentionally tiny:

- a small opacity volume,
- a handful of light angles,
- tiny binary target images,
- differentiable rendering,
- gradient-based optimization,
- visualization of convergence.

The goal is understanding rather than engineering a practical sundial.

---

## 7. Beyond sundials

Although inspired by passive digital sundials, the broader repository explores learned passive optical geometry more generally, including passive displays, artistic shadow projection, inverse projection geometry, compressed physical representations, and related inverse-design problems.

---

## 8. Relationship to employer resources

Development occurs independently on personal systems using public mathematics and independently developed experimentation. No employer datasets, confidential workflows, or proprietary implementations are used.

---

## 9. Repository scope

The repository may include optimization experiments, rendering utilities, visualization notebooks, geometry generators, reproducibility helpers, experiment documentation, and printable prototype generation.

It excludes proprietary CAD assets, confidential data, employer materials, and restricted implementations.

---

## 10. Development roadmap

### Lean-to

- tiny differentiable renderer
- simple opacity volume
- binary target images
- optimization visualization
- reproducible notebook

### Cabin

- larger digit displays
- improved parameterizations
- printable geometries
- multiple optimization strategies

### Cathedral

Potential future work includes reduced-dimensional parameterizations<sup>[2]</sup>, passive computational optics, broader inverse physical design, educational publications, and research notes.

Future work should be earned through successful intermediate experiments.

---

## 11. Portfolio value

The project demonstrates machine-learning intuition, optimization, computational geometry, visualization, reproducibility, and technical communication.

---

## 12. Closing summary

Design by Inverse Angular Light begins with a simple question:

> Can a machine learn the shape of an object from the shadows we wish it to cast?

The immediate goal is a small, interpretable portfolio-quality demonstration. The broader vision is a family of learned passive optical structures grounded in public mathematics, independent development, and incremental experimentation.

---

## 13. Footnotes

### 13.1. Footnote on names

[1]: "DIAL" is the project's working name and recalls the digital sundial that inspired it.

Experiment 0 is informally called **Deep Shadow Learners (DSL)**. As the project evolves, DSL could equally stand for *Differentiable* or *Density Shadow Learners*.

A playful backronym survives in the notes:

> **Shadow Understanding through Neural Design by Inverse Angular Light**

It is retained for fun rather than as the formal project title.

### 13.2. Footnote on representations

[2]: On reduced-dimensional parameterizations

#### 13.2.1. How much of the problem space is wortless? 

The initial implementation intentionally adopts a general three-dimensional opacity field (for example, a voxel or density representation) because it is conceptually simple and places few restrictions on the optimization process. However, the author suspects that this representation is substantially higher-dimensional than the underlying design problem requires.

Unlike a general inverse-rendering problem, the illumination directions of interest are highly constrained. For a passive sundial, the Sun follows a predictable family of trajectories determined by latitude, season, and time of day. Consequently, only a relatively small subset of all possible incident light directions contributes to the optimization objective.

This raises the possibility that the design space itself admits a lower-dimensional parameterization. Rather than optimizing an arbitrary volumetric density field, future work may explore representations based on geometric primitives, layered structures, sparse blocking elements, learned basis functions, or other compressed descriptions that better reflect the constrained geometry of the illumination.

**One way to think about this is that the optimizer may not need to describe "every possible object," but only objects that behave correctly under a restricted family of ray bundles. Discovering an efficient representation for that restricted design space may ultimately prove more interesting than optimizing a dense voxel grid itself.**

At present, this idea is intentionally treated as a research question rather than a design assumption. The first experiments deliberately begin with the more general representation because it is easier to understand, visualize, and implement. If those experiments succeed, investigating lower-dimensional parameterizations may become one of the project's most interesting directions.

#### 13.2.2. Will such representations be physically meaningful?

One speculative intuition motivating this direction is that optimization variables should ideally correspond to meaningful engineering decisions rather than arbitrary discretizations of space. A representation whose parameters naturally describe moving a wall, thickening a rib, extending a blocker, or otherwise modifying physically interpretable structures could provide both computational advantages and greater insight into the geometry being learned. Whether such a representation exists, and whether it can be optimized as effectively as a dense volumetric field, remains an open question.

---

*End of document*
