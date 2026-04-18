# edge-camera-sbc-selective-parallelization

TeX source, figures, and bibliography for the paper **“Edge Camera Based on a Single-Board Computer: Hybrid Selective Parallelization in Real-Time Video Processing.”**

## Overview

This repository contains the LaTeX source of a CEUR-style research paper devoted to the design and evaluation of a low-cost SBC-based edge camera for real-time video preprocessing. The study investigates whether selective parallelization of primitive image-processing stages can enable real-time performance on resource-constrained hardware.

The experimental prototype is based on an **Orange Pi Zero 2W** and a **Logitech C170 USB camera**. The evaluated processing chain includes **Laplacian filtering**, **histogram computation**, and **Gaussian blurring**. Under the reported test conditions, the hybrid parallel-sequential implementation improves throughput from **24 FPS** to **28 FPS**, satisfying the adopted **25 FPS** real-time criterion.

## Repository Purpose

This repository is intended to provide:

- the manuscript source in LaTeX;
- the bibliography used for the paper;
- figure assets required for compilation;
- a clean and reproducible basis for further revision and submission.