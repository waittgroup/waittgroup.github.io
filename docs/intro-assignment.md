# Introductory Assignment: Meet ASE, the G2 Database, and Your Molecules

This is your first hands-on introduction to the tools you'll be using
throughout your time in the group. Complete this after finishing the
setup steps in the [New Member Guide](new-member-guide.md).

## Overview

You'll use the Atomic Simulation Environment (ASE) to explore a
standard benchmark set of small molecules (the G2 database), compute
some basic statistics, then bridge that same set of molecules into
RDKit to see how a cheminformatics tool "sees" the same chemistry
differently than a quantum chemistry tool does. You'll finish by
making a few plots that summarize what you found.

No prior chemistry-coding experience is assumed. Every section builds
directly on the one before it.

## Learning objectives

By the end of this assignment, you should be able to:

- Load and inspect a molecular database using ASE
- Extract basic properties (composition, atomic masses) from ASE
  `Atoms` objects
- Compute summary statistics (mean, standard deviation) over a
  collection of molecules
- Load molecules into RDKit and compute basic molecular descriptors
- Compare and cross-check values obtained from two different tools
- Produce clear, labeled plots that communicate a dataset's properties

## Part 1: Meet ASE and the G2 database

Get oriented with ASE's built-in G2 collection — a standard set of
small molecules originally assembled for benchmarking quantum
chemistry methods, and one you'll see again in later work.

Tasks:

- Load the G2 collection and figure out how to list all molecule
  names it contains
- Report the total number of molecules in the database
- For a few individual molecules, inspect their chemical formula and
  atomic composition
- Briefly note (2–3 sentences) what kind of information an ASE
  `Atoms` object does and does not contain — this will matter in
  Part 3

## Part 2: Molecular mass statistics

Now treat the database as a dataset rather than a collection of
individual curiosities.

Tasks:

- For every molecule in G2, compute its total molecular mass
- Report the average molecular mass across the entire database
- Report the standard deviation of molecular mass across the database
- Identify the lightest and heaviest molecules in the set by name

## Part 3: Exposure to RDKit

ASE knows atomic positions and masses, but it doesn't know bonding or
molecular structure the way a cheminformatics tool does. In this part,
you'll load the same molecules into RDKit (using a provided name →
SMILES mapping, since G2 doesn't include bonding information) and see
what a different tool can tell you about the same chemistry.

Tasks:

- Load a subset of the G2 molecules into RDKit from their SMILES
  strings
- Compute a small set of standard RDKit descriptors for each (at
  minimum: molecular weight, LogP, and number of heavy atoms)
- Cross-check: compare RDKit's molecular weight against the mass you
  computed from ASE in Part 2 for the same molecules. Do they agree?
  If not, briefly speculate why.

## Part 4: Plotting exercises

Turn your results into a small set of clear figures. For each plot,
include axis labels, a title, and 1–2 sentences describing what it
shows.

Suggested plots:

- A histogram of molecular masses across the full G2 database
- A bar chart of element frequency across the database (which
  elements show up most often?)
- A scatter plot comparing ASE-derived mass vs. RDKit molecular weight
  for your Part 3 subset (this should look like a nearly perfect line
  — a good sanity check on your own work)
- One plot of your choice using any RDKit descriptor from Part 3

## Deliverables

A single Jupyter notebook containing:

- All code cells, run in order, with outputs visible
- Short markdown commentary above each part explaining what you did
- Answers to the specific questions above (formula counts,
  average/std dev, lightest/heaviest molecule, cross-check discussion)
- All four plots with labels and brief interpretive notes

## Notes

- This is meant to be exploratory — if you get curious about a
  molecule or a pattern in the data, follow it and note what you
  found.
- The ASE/RDKit cross-check in Part 3 is a habit worth keeping:
  whenever two tools should agree, checking that they actually do is
  good practice, not busywork.
