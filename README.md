[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/yfSNuVM-)



# CRISM Hyperspectral Composition Mapping (Mars, Nili Fossae)

This project implements a two-stage pipeline for mineralogical classification of the Martian surface using CRISM MTRDR hyperspectral data.

## Overview

The system combines:

- **Unsupervised clustering** (MiniBatchKMeans) to generate spectral clusters
- **Supervised classification** (1D CNN) trained on the cluster labels
- Full pipeline tested on **137 cubes** covering the Nili Fossae region

All code is written in Python using NumPy, PyTorch, and scikit-learn. The workflow runs in memory-safe mode on local machines.

## Features

- Preprocessing with stitching artefact removal and per-band standardisation
- Chunked processing of 23M+ spectra without exceeding RAM
- Visual labelmaps and disagreement analysis
- Final overview map showing predicted surface compositions

## Folder Structure

```bash
├── data/                         # (ignored) Raw and preprocessed CRISM data
├── notebooks/                   # Jupyter notebooks for each pipeline stage
├── outputs/
│   ├── cnn_labelmaps_20_epochs/
│   ├── map_tests/
├── results/
│   ├── clustering/              # Cluster labels
│   ├── labelmaps/              # Spatial labelmaps (e.g. k=8)
├── .gitignore
├── README.md

