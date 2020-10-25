# Deep Slow Motion Video Reconstruction with Hybrid Imaging System



## Abstract

Slow motion videos are becoming increasingly popular, but capturing high-resolution videos at extremely high frame rates requires professional high-speed cameras. To mitigate this problem, current techniques increase the frame rate of standard videos through frame interpolation by assuming linear object motion which is not valid in challenging cases. In this paper, we address this problem using two video streams as input; an auxiliary video with high frame rate and low spatial resolution, providing temporal information, in addition to the standard main video with low frame rate and high spatial resolution. We propose a two-stage deep learning system consisting of alignment and appearance estimation that reconstructs high resolution slow motion video from the hybrid video input. For alignment, we propose to compute flows between the missing frame and two existing frames of the main video by utilizing the content of the auxiliary video frames. For appearance estimation, we propose to combine the warped and auxiliary frames using a context and occlusion aware network. We train our model on synthetically generated hybrid videos and show high-quality results on a variety of test scenes. To demonstrate practicality, we show the performance of our system on two real dual camera setups with small baseline.

[[paper]](https://arxiv.org/pdf/2002.12106.pdf) [[code]](https://github.com/avinashpaliwal/Deep-SloMo)

