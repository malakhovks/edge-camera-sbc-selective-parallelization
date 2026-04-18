# edge-camera-sbc-selective-parallelization

TeX source, figures, and bibliography for the paper **“Edge Camera Based on a Single-Board Computer: Hybrid Selective Parallelization in Real-Time Video Processing.”**

## Authors

### Oleksii V. Bahatskyi

V.M. Glushkov Institute of Cybernetics of the National Academy of Sciences of Ukraine, Kyiv, Ukraine
Borys Grinchenko Kyiv Metropolitan University, Kyiv, Ukraine

### Kyrylo S. Malakhov

V.M. Glushkov Institute of Cybernetics of the National Academy of Sciences of Ukraine, Kyiv, Ukraine
Corresponding author

## Correspondence

For academic correspondence regarding the manuscript, please contact the corresponding author indicated in the paper.

## Overview

This repository contains the LaTeX source code and supporting materials for a CEUR-style research paper on an SBC-based edge camera for real-time video preprocessing.

The paper investigates whether a low-cost single-board computer can satisfy real-time constraints for a lightweight video-processing pipeline composed of primitive transformations. The proposed implementation combines a staged processing chain with selective parallelization of computationally intensive operations in order to improve throughput on resource-constrained hardware.

The experimental prototype is based on an **Orange Pi Zero 2W** and a **Logitech C170 USB camera**. The evaluated processing workflow includes:

- **Laplacian filtering**
- **Histogram computation**
- **Gaussian blurring**

Under the reported test conditions, the hybrid parallel-sequential implementation improves throughput from **24 FPS** to **28 FPS**, thereby satisfying the adopted **25 FPS** real-time criterion.

## Repository Contents

This repository is intended to provide a clean and reproducible source package for paper preparation, revision, and submission.

Typical contents include:

- main LaTeX manuscript source;
- bibliography database;
- figure files used in the paper;
- compiled PDF output;
- auxiliary repository documentation.

## Main Files

- `bahatskyi_malakhov_ukrprog_2026.tex` — main manuscript source
- `bahatskyi_malakhov_ukrprog_2026.pdf` — compiled paper draft
- `sample-ceur.bib` or equivalent `.bib` file — bibliography database
- figure/image files used in the manuscript
- `README.md` — repository description

## Abstract-Level Summary

The paper addresses the design and evaluation of a low-cost edge camera that performs latency-sensitive preprocessing directly on the device, near the data source. The software architecture is implemented in **C++14** with **OpenCV** and uses a hybrid execution model in which selected stages are parallelized while others remain sequential.

The main contribution is the demonstration that selective parallelization of a primitive transformation chain can be sufficient to move an SBC-based vision node from near-real-time to real-time operation under constrained hardware conditions.

## Hardware and Software Context

### Hardware
- **Orange Pi Zero 2W**
- **Allwinner H618**
- **Quad-core ARM Cortex-A53 @ 1.5 GHz**
- **4 GB RAM**
- **Logitech C170 USB camera**
- **640 × 480** frame resolution
- **YUYV** color encoding

### Software
- **Ubuntu 22.04.4 LTS**
- **Linux kernel 6.1.31-sun50iw9**
- **g++ 12.3.0**
- **C++14**
- **OpenCV 4.10**

## Research Focus

The manuscript is centered on the following questions:

1. Can a low-cost SBC function as an edge video node for real-time preprocessing?
2. How should a user-space processing pipeline be organized for constrained multi-core hardware?
3. Does selective parallelization provide a measurable and practically useful performance gain?
4. To what extent does the resulting architecture conform to the edge-computing paradigm?

## Processing Pipeline

The evaluated transformation chain consists of three stages:

1. **Laplacian filtering**
2. **Histogram computation**
3. **Gaussian blurring**

Two execution modes are compared:

- **Sequential mode** — all stages executed sequentially
- **Hybrid mode** — Laplacian filtering parallelized, remaining stages sequential

## Key Result

The principal experimental finding is that the fully sequential version achieves **24 FPS**, whereas the hybrid parallel-sequential implementation reaches **28 FPS**, corresponding to an approximate **16.7%** throughput improvement.

This result indicates that low-cost SBC platforms can support lightweight edge-side preprocessing tasks when the computational structure is carefully designed.

## Build Instructions

Compile the manuscript using a standard LaTeX and BibTeX workflow:

```bash
pdflatex bahatskyi_malakhov_ukrprog_2026.tex
bibtex bahatskyi_malakhov_ukrprog_2026
pdflatex bahatskyi_malakhov_ukrprog_2026.tex
pdflatex bahatskyi_malakhov_ukrprog_2026.tex
```