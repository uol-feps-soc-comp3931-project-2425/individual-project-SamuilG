[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/yfSNuVM-)


# Surface Composition Mapping of Mars Using Pseudo-Labels and a Convolutional Learning Pipeline  
**CRISM Hyperspectral Composition Mapping (Mars, Nili Fossae)**

This project implements a complete machine learning pipeline for pixel-wise classification of Martian surface materials using hyperspectral data from NASA's CRISM instrument. It combines unsupervised clustering and supervised deep learning to generate mineralogical maps of the Nili Fossae region without requiring manual labels.

## Environment

- Python 3.9.22
- OS: Red Hat Enterprise Linux 9.5 (Plow)
- GPU: NVIDIA RTX 4070 (12GB VRAM)
- RAM: 32GB
- Managed via `conda`, **no `pip` used**


## Not Included in Git

This repository **excludes** the following:

- Raw hyperspectral cubes (`/data`)
- Preprocessed `.npy` arrays
- Conda virtual environment folder (`hyperenv`)


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
```

## Requirements

Run inside a Conda environment. Key libraries:

- Python 3.9
- NumPy 2.0.2
- PyTorch 2.6.0
- scikit-learn 1.6.1
- matplotlib
- tqdm
- pandas
- skimage
- spectral

> All libraries were installed using **conda only**, without pip.

## Notes

- `data/`, `.npy` files, and `hyperenv/` are excluded from version control
- The final CNN was trained for 20 epochs with 88.78% validation accuracy
- Average disagreement between CNN and clustering: 14.97% across 28 cubes
- All figures and metrics were generated using reproducible notebooks



