# Super SloMo: High Quality Estimation of Multiple Intermediate Frames for Video Interpolation



## Abstract

Given two consecutive frames, video interpolation aims at generating intermediate frame(s) to form both spatially and temporally coherent video sequences. While most existing methods focus on single-frame interpolation, we propose an end-to-end convolutional neural network for **variable-length** multi-frame video interpolation, where the **motion interpretation and occlusion reasoning are jointly modeled**. We start by computing **bi-directional optical flow** between the input images using a U-Net architecture. These flows are then **linearly combined at each time step** to approximate the intermediate bi-directional optical flows. These approximate flows, however, only work well in locally smooth regions and produce artifacts around motion boundaries. To address this shortcoming, we employ another UNet to refine the approximated flow and also predict soft visibility maps. Finally, the two input images are warped and linearly fused to form each intermediate frame. By applying the visibility maps to the warped images before fusion, we exclude the contribution of occluded pixels to the interpolated intermediate frame to avoid artifacts. Since none of our learned network parameters are time-dependent, our approach is able to produce as many intermediate frames as needed. To train our network, we use 1,132 240-fps video clips, containing 300K individual video frames. Experimental results on several datasets, predicting different numbers of interpolated frames, demonstrate that our approach performs consistently better than existing methods.

[[paper]](https://arxiv.org/pdf/1712.00080.pdf) [[project]](https://people.cs.umass.edu/~hzjiang/projects/superslomo/)



## Method

**Temporal Consistency and Occlusion Reasoning with Backward Warping Function** 

![interpolation](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SuperSloMo/interpolation.png)

**Unsupervised Optical-flow Estimation**

![flow](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SuperSloMo/flow.png)

![flow2](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SuperSloMo/flow2.png)

$$\widehat{F}_t\to1=(1-t)F_0\to1$$ 

**Framework**

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SuperSloMo/framework.png)