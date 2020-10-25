# Depth-Aware Video Frame Interpolation



## Abstract

Video frame interpolation aims to synthesize non- existent frames in-between the original frames. While sig- nificant advances have been made from the recent deep convolutional neural networks, the quality of interpola- tion is often reduced due to large object motion or occlu- sion. In this work, we propose a video frame interpola- tion method which explicitly detects the occlusion by ex- ploring the depth information. Specifically, we develop a depth-aware flow projection layer to synthesize intermedi- ate flows that preferably sample closer objects than far- ther ones. In addition, we learn hierarchical features to gather contextual information from neighboring pixels. The proposed model then warps the input frames, depth maps, and contextual features based on the optical flow and lo- cal interpolation kernels for synthesizing the output frame. Our model is compact, efficient, and fully differentiable. Quantitative and qualitative results demonstrate that the proposed model performs favorably against state-of-the-art frame interpolation methods on a wide variety of datasets.

[[paper]](https://arxiv.org/pdf/1904.00830.pdf) [[code]](https://github.com/baowenbo/DAIN)

