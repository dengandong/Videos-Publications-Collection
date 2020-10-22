# Video Generation from Single Semantic Label Map



## Introduction

This paper proposes the novel task of video generation conditioned on a SINGLE semantic label map, which provides a good balance between flexibility and quality in the generation process. Different from typical end-to-end approaches, which model both scene content and dynamics in a single step, we propose to decompose this difficult task into two sub-problems. As current image generation methods do better than video generation in terms of detail, we synthesize high quality content by only generating the first frame. Then we animate the scene based on its semantic meaning to obtain temporally coherent video, giving us excellent results overall. We employ a cVAE for predicting optical flow as a beneficial intermediate step to generate a video sequence conditioned on the initial single frame. A semantic label map is integrated into the flow prediction module to achieve major improvements in the image-to-video generation process. Extensive experiments on the Cityscapes dataset show that our method outperforms all competing methods.

[[paper]](https://arxiv.org/pdf/1903.04480v1.pdf) [[code]](https://github.com/junting/seg2vid)



## Framework

![seg2vid](https://github.com/antony0621/Publications-of-Video/blob/master/pics/Seg2Vid/Seg2Vid.png)
