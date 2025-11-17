# Micro-Fracture Segmentation in Volcanic Reservoir Using Esemble-Learning and Deep-Learning

**Manuscript title：** Connectivity of Micro-fractures and Gas Migration Mechanisms in Volcanic Reservoirs Based on μCT and Deep Learning.
**Authors:** zjc25@mails.jlu.edu.cn (J.C. Zhang); yuyunliang@jlu.edu.cn (Y.L. Yu); caihc24@mails.jlu.edu.cn (H.C. Cai); mengyul25@mails.jlu.edu.cn (M.Y. Li); ycliu23@mails.jlu.edu.cn (Y.C. Liu)

## What is this
Reproducible code, sample data and softwares for the manuscript in different stages. This repo contains:
-Software installation package: Imagej-Windows64, Dragonfly 2024.01.
-Code for achieving automated application of random forest model in software Imagej ('/src')
-User manual ('/docs/USER_MANUAL.md')
-Test data ('/data/sample') and expected outputs ('outputs_expected')


## Quick start
Install software Imagej and Dragonfly.
Run code in Imagej to achieve automated application of the random forest model for every raw samples.
Put semgemented samples into Dragonfly and run 2.5D U-Net++ model for 3D grayscale volume.
