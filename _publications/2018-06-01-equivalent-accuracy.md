---
title: "Equivalent-accuracy Accelerated Neural-network Training Using Analogue Memory"
collection: publications
permalink: /publications/2018-06-01-equivalent-accuracy
excerpt: 'Neural-network training can be slow and energy intensive, owing to the need to transfer the weight data for the network between conventional digital memory chips and processor chips. Analogue non-volatile memory can accelerate the neural-network training algorithm known as backpropagation by performing parallelized multiply–accumulate operations in the analogue domain at the location of the weight data.'
date: 2018-06-01
venue: 'Nature'
paperurl: 'https://doi.org/10.1038/s41586-018-0180-5'
citation: 'Ambrogio, S., Narayanan, P., Tsai, H. et al. Equivalent-accuracy accelerated neural-network training using analogue memory. Nature 558, 60–67 (2018). https://doi.org/10.1038/s41586-018-0180-5.'
---

## Abstract

Neural-network training can be slow and energy intensive, owing to the need to transfer the weight
data for the network between conventional digital memory chips and processor chips. Analogue
non-volatile memory can accelerate the neural-network training algorithm known as backpropagation
by performing parallelized multiply–accumulate operations in the analogue domain at the location of
the weight data. However, the classification accuracies of such in situ training using
non-volatile-memory hardware have generally been less than those of software-based training, owing
to insufficient dynamic range and excessive weight-update asymmetry. Here we demonstrate mixed
hardware–software neural-network implementations that involve up to 204,900 synapses and that
combine long-term storage in phase-change memory, near-linear updates of volatile capacitors and
weight-data transfer with ‘polarity inversion’ to cancel out inherent device-to-device
variations. We achieve generalization accuracies (on previously unseen data) equivalent to those of
software-based training on various commonly used machine-learning test datasets (MNIST,
MNIST-backrand, CIFAR-10 and CIFAR-100). The computational energy efficiency of 28,065 billion
operations per second per watt and throughput per area of 3.6 trillion operations per second per
square millimetre that we calculate for our implementation exceed those of today’s graphical
processing units by two orders of magnitude. This work provides a path towards hardware
accelerators that are both fast and energy efficient, particularly on fully connected
neural-network layers.

[Read more.](https://doi.org/10.1038/s41586-018-0180-5)

**See also:** [Efficient Processing of Convolutional Neural Network Layers Using
Analog-memory-based Hardware](https://benjamindkilleen.com/publications/2020-04-16-efficient-processing)
