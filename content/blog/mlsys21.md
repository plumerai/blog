---
title: "MLSys 2021: Design, Benchmark, and Deploy Binarized Neural Networks with Larq Compute Engine"
subtitle: ""
heroImage: ""
date: 2021-04-07T00:05:36+02:00
draft: false
socialTitle: "MLSys 2021: Design, Benchmark, and Deploy Binarized Neural Networks with LCE"
socialDescription: "We are very excited to present our paper about Larq Compute Engine at MLSys 2021!"
socialImage: "images/mlsys21/mlsys-announcement-social.png"
---

We are very excited to present our paper [Larq Compute Engine: Design, Benchmark, and Deploy State-of-the-Art Binarized Neural Networks](https://proceedings.mlsys.org/paper/2021/file/c7e1249ffc03eb9ded908c236bd1996d-Paper.pdf) at the [MLSys 2021](https://mlsys.org/) conference this week!

[Larq Compute Engine](https://docs.larq.dev/compute-engine/) (LCE) is a state-of-the-art inference engine for Binarized Neural Networks (BNNs).
LCE makes it possible for researchers to easily benchmark BNNs on mobile devices.
Real latency benchmarks are essential for developing BNN architectures that actually run fast on device, and we hope LCE will help people to build even better BNNs.

In the [paper](https://proceedings.mlsys.org/paper/2021/file/c7e1249ffc03eb9ded908c236bd1996d-Paper.pdf), we discuss the design of LCE and go into the technical details behind the framework.
LCE was designed for usability and performance.
It extends [TensorFlow Lite](https://www.tensorflow.org/lite), which makes it possible to integrate binarized layers into any model supported by TFLite and run it with LCE.
Integration with [Larq](https://docs.larq.dev/larq/) makes it very easy to move from training to deployment.
And thanks to our hand-optimized inference kernels and sophisticated MLIR-based graph optimizations, inference speed is phenomenal.

![12x - 17x speedup from binarization](/images/mlsys21/binarization-speedup.svg)
_The impact of binarization on the latency of different convolutional blocks in ResNets - binary is up to 17x faster than 32-bit floating point and 12x faster than 8-bit integers on a Pixel 1 phone._

BNNs are all about efficient inference: their tiny memory footprint and compact bitwise computations make them perfect for edge applications and small, battery powered devices.
However, this requires the people building BNNs to have access to real, empirical measurements of their model as it is deployed.
Lacking the right tools, researchers too often refrain to proxy metrics such as the number of FLOPs.
LCE aims to change this.

In the paper, we demonstrate the value of measuring latency directly by analyzing the execution of some of the best existing BNN designs, such as [R2B](https://arxiv.org/abs/2003.11535) and [BinaryDenseNets](https://openaccess.thecvf.com/content_ICCVW_2019/html/NeurArch/Bethge_BinaryDenseNet_Developing_an_Architecture_for_Binary_Neural_Networks_ICCVW_2019_paper.html).
We identify suboptimal points in these models and present QuickNet, a new model family which outperforms all existing BNNs on ImageNet in terms of latency and accuracy.

![Breakdown of QuickNet latency](/images/mlsys21/quicknet-breakdown.svg)
_Breakdown of the latency of QuickNet-Large (QNL), our new state-of-the-art BNN.
Note how compared to Real-to-Binary Net (R2B) and BinaryDenseNet, we win mostly on the high-precision first layer and ‘glue’ layers._

We will be presenting the work at the MLSys conference on Wednesday the 7th of April.
The published [paper](https://proceedings.mlsys.org/paper/2021/file/c7e1249ffc03eb9ded908c236bd1996d-Paper.pdf) is publicly available, and registered attendees will be able to view our oral talk.
We hope you will all attend, and if you want to learn more about running BNNs on all sorts of devices, contact us at [hello@plumerai.com](mailto:hello@plumerai.com)!
