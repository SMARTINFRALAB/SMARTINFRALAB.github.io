---
title: "Observability-based sensor placement improves contaminant tracing in river networks"
collection: publications
permalink: /publication/2020-09-02-observability
excerpt: ''
date: 2020-09-02
venue: 'Earth and Space Science Open Archive'
type: 'preprint'
paperurl: 'https://www.essoar.org/doi/10.1002/essoar.10504108.1'
file: 'https://mdbartos.s3.us-east-2.amazonaws.com/publications/observability_based_sensor_placement.pdf'
filetype: 'Preprint version'
citation: '<b>Bartos, M.</b>, & Kerkez, B. (2021). Observability-based sensor placement improves contaminant tracing in river networks. doi: 10.1002/essoar.10504108.1 (submitted to <i>Water Resources Research</i>).'
abstract_art: 'https://mdbartos.s3.us-east-2.amazonaws.com/img/abstract_art_12.png'
abstract_art_caption: 'Visualization of sensor placements predicted by observability maximization. Sensor placement progression for trace- (left) and rank- (right) optimized strategies from N=2 to N=16 sensors.'
tags: ['state-estimation', 'networks']
---

## Abstract

This study presents a new methodology for identifying near-optimal sensor locations for contaminant source tracing in river networks. To establish a physical basis for the problem, we first derive a linear time-invariant (LTI) model for riverine contaminant transport using the one-dimensional advection-diffusion equation. We then formulate an optimization problem to find the sensor placement that maximizes the observability of the modeled system, and identify two heuristics for efficiently achieving this goal. Evaluating each sensor placement strategy on its ability to reconstruct initial contaminant loads from observed outputs, we find that the best sensor placement is obtained by greedily maximizing the rank of the LTI system's Observability Gramian. In addition to providing the best approximate reconstruction of internal states, this strategy makes it possible to perfectly recover any initial contaminant load while only monitoring a small subset of river branches (~14%). Our methodology will enable researchers to build sensor networks that better interpolate pollutant loads in ungaged locations, improve contaminant source identification, and inform more effective pollution control strategies.
