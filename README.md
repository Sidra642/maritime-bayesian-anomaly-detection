# Confidence-Aware Bayesian Maritime Anomaly Detection

## Overview

This research prototype explores vessel detection in satellite imagery and Bayesian spatial anomaly scoring to identify areas with unusually high vessel activity.

The project combines a convolutional neural network (CNN) for patch-level vessel classification with sliding-window inference, non-maximum suppression, spatial tile aggregation, and a Gamma–Poisson predictive model with multiple-testing correction.

## Research Motivation

Vessel detections from satellite imagery can be uncertain. This prototype investigates how probabilistic modeling can help distinguish unusual spatial activity from expected background variation while accounting for false alarms.

## Methodology

1. Train and evaluate a CNN using labeled satellite image patches.
2. Apply sliding-window inference to larger satellite scenes.
3. Aggregate detections into spatial tiles.
4. Estimate expected tile counts using a Bayesian Gamma–Poisson model.
5. Calculate predictive tail probabilities and apply Benjamini–Hochberg correction.

## Preliminary Results

- Patch-level classification accuracy: 93.5%
- Patch-level ROC-AUC: 0.9809
- Satellite scenes analyzed: 8
- Sliding windows evaluated: 19,821
- Detections after non-maximum suppression: 62
- Spatial tiles analyzed: 240
- Tiles flagged at the baseline setting after multiple-testing correction: 1

These are preliminary results from a small set of scenes. The random patch split does not establish generalization to geographically independent scenes. The anomaly flags also require more ground-truth validation; they should not be interpreted as confirmed maritime threats or as proof of a reduced false-alarm rate.

## Limitations and Future Work

- Validate on geographically independent scenes and annotated vessel locations.
- Quantify detection uncertainty and its effect on anomaly scores.
- Compare against simpler count-based and heterogeneous-intensity baselines.
- Investigate how uncertainty-aware anomaly estimates could inform limited-budget sensor placement.

## Reproducibility

The notebook, analysis outputs, and environment requirements are provided in this repository. See the notebook for implementation details and the dataset source for access instructions.

## Dataset

Ships in Satellite Imagery dataset: https://www.kaggle.com/datasets/rhammell/ships-in-satellite-imagery

## Disclaimer

This is an exploratory research prototype, not an operational maritime surveillance or threat-detection system.
