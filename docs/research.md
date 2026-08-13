# Research

_Last updated: 2026-07-19_

The Waitt Group works at the intersection of computational chemistry,
bioinformatics, and taste science. We combine quantum-mechanical (QM)
molecular descriptors, receptor sequence analysis, and machine
learning to understand and predict how molecules and receptors drive
taste perception.

## Research areas

### Cheminformatics & QM-derived descriptors

Computing quantum-mechanical descriptors (e.g. via ORCA) and
conventional 2D/topological descriptors (via RDKit) for small
molecules relevant to taste perception, as inputs for downstream ML
models.

### Bioinformatics & receptor-ligand analysis

Analyzing taste receptor sequences — starting with the human bitter
taste receptor family (TAS2Rs) — using tools like BLAST to compare
receptors and relate sequence similarity to shared ligand binding.

### ML for taste prediction

Building machine learning models that predict taste properties and
receptor-ligand associations from molecular descriptors and
sequence-derived features alike.

### Computational workflows

Scaling both QM calculations and sequence/ML workflows using
containerized tools on OSPool/HTCondor — see the [SOPs](sops/ospool-account-setup.md)
section for current workflows, starting with
[ORCA on OSPool](sops/orca-ospool-workflow.md).

## Active projects

### QM-Enhanced Machine Learning for Bitter Taste Prediction

_Cheminformatics_

This project investigates whether quantum mechanical (QM) molecular
descriptors improve machine learning predictions of bitter taste
compared to standard structural descriptors alone. Using BitterDB's
curated dataset of over 2,400 bitter compounds, we first establish a
baseline model using conventional 2D/topological molecular descriptors
(via RDKit), then augment it with QM-derived electronic properties
(HOMO/LUMO gap, dipole moment, electrostatic potential) calculated
using ORCA. By comparing model performance with and without QM
features, this work tests whether a molecule's electronic structure
carries predictive signal beyond what's captured by its 2D structure —
with implications for how we computationally model taste perception.

### Sequence Similarity and Ligand Sharing Among Bitter Taste Receptors

_Bioinformatics_

This project explores whether the sequence similarity of human bitter
taste receptors (TAS2Rs) predicts whether they respond to the same
bitter compounds. Using BLAST-based sequence comparison across all 25
human TAS2R genes and receptor-ligand association data from BitterDB,
we quantify the relationship between receptor sequence similarity and
shared ligand profiles. The project also incorporates an exploratory
machine learning component using sequence-derived features to predict
receptor-ligand associations, providing a foundation for future work
extending this analysis across species using BitterDB's growing
cross-species receptor database.
