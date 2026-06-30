<!-- File: IP_Notes_-_DIAL_DSL_Experiment_000_2026-06-30.md -->

# IP Notes — DIAL / DSL — Experiment 000

**Filename:** `IP_Notes_-_DIAL_DSL_Experiment_000_2026-06-30.md`  
**Project:** Design by Inverse Angular Light (DIAL)  
**Experiment:** Deep Shadow Learners (DSL) — Experiment 000  
**Date:** 2026-06-30

---

# Purpose

Experiment 000 exists to answer one question:

> Can gradient-based optimization learn a tiny passive optical object whose
> projected shadows match a small set of desired binary images?

This is intentionally a learning experiment and portfolio artifact rather
than an engineering-quality digital sundial.

---

# Success Criteria

Success does **not** require:

- astronomical accuracy,
- printable geometry,
- a complete clock,
- minute-level resolution,
- or fabrication.

Success **does** require:

- a working differentiable optimization loop,
- visible convergence,
- reproducible code,
- and a clear explanation of why the optimization works.

---

# Scope

Input:

- small collection of illumination angles
- fixed projection plane
- fixed camera / observer geometry

Learned object:

- tiny 3D opacity volume
- continuous values in [0,1]

Output:

- projected binary image

Optimization:

- gradient descent
- differentiable renderer
- image loss

---

# Initial target

Keep the first experiment intentionally tiny.

Possible targets:

- 3×3 binary patterns
- 5×8 digit
- eight illumination angles
- eight desired projections

The emphasis is understanding, not realism.

---

# Representation

Experiment 000 deliberately uses the simplest representation:

- dense voxel / opacity tensor

Future experiments may compare:

- run-length encoded slice representations
- wall-gap parameterizations
- geometric primitives
- reduced-dimensional parameterizations

These are explicitly out of scope for Experiment 000.

---

# Questions to answer

1. Does optimization converge?

2. What loss function behaves best?

3. How sensitive is convergence to initialization?

4. How expensive is rendering?

5. Which visualizations best explain the optimization?

---

# Possible repository structure

```text
dial/

README.md
PROJECT_CONTEXT.md

docs/
    Project_Charter.md
    experiment_000.md

notebooks/
    000_explore_geometry.ipynb
    010_first_optimizer.ipynb
    020_visualizations.ipynb

src/dial/
    renderer.py
    optimizer.py
    geometry.py
    losses.py
    visualization.py
    experiments.py

tests/

assets/
    figures/
    animations/

results/
```

Names are intentionally provisional.

---

# Stretch goals (not required)

- animation of optimization
- STL export
- printable prototype
- larger digit resolution
- seasonal sun paths

These should not delay completion.

---

# Future ideas captured for later

Interesting directions intentionally postponed:

- compressed slice encodings
- run-length wall/gap parameterizations
- reduced-dimensional geometric representations
- engineering primitive representations
- full passive digital sundial
- broader passive optical computation

These belong to future experiments after Experiment 000 succeeds.

---

# Philosophy

Experiment 000 is successful if it teaches something.

It is not expected to answer every research question raised by the broader
Design by Inverse Angular Light vision.

The experiment should remain small enough to finish in roughly one week,
while demonstrating optimization, geometry, visualization, and clear
technical communication.

---

*End of document*
