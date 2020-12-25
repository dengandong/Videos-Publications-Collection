# MirrorFlow: Exploiting Symmetries in Joint Optical Flow and Occlusion Estimation


## Abstract

Optical flow estimation is one of the most studied prob- lems in computer vision, yet recent benchmark datasets continue to reveal problem areas of today’s approaches. Occlusions have remained one of the key challenges. In this paper, we propose a symmetric optical flow method to ad- dress the well-known chicken-and-egg relation between op- tical flow and occlusions. In contrast to many state-of- the-art methods that consider occlusions as outliers, possibly filtered out during post-processing, we highlight the importance of joint occlusion reasoning in the optimization and show how to utilize occlusion as an important cue for estimating optical flow. The key feature of our model is to fully exploit the symmetry properties that characterize optical flow and occlusions in the two consecutive images. Specifically through utilizing forward-backward consistency and occlusion-disocclusion symmetry in the energy, our model jointly estimates optical flow in both forward and backward direction, as well as consistent occlusion maps in both views. We demonstrate significant performance benefits on standard benchmarks, especially from the occlusion-disocclusion symmetry. On the challenging KITTI dataset we report the most accurate two-frame results to date.

[paper](https://arxiv.org/pdf/1708.05355.pdf)



## Method

