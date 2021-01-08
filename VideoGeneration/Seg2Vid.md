# Video Generation from Single Semantic Label Map



## Introduction

This paper proposes the novel task of video generation conditioned on a SINGLE semantic label map, which provides a good balance between flexibility and quality in the generation process. Different from typical end-to-end approaches, which model both scene content and dynamics in a single step, we propose to decompose this difficult task into two sub-problems. As current image generation methods do better than video generation in terms of detail, we synthesize high quality content by only generating the first frame. Then we animate the scene based on its semantic meaning to obtain temporally coherent video, giving us excellent results overall. We employ a cVAE for predicting optical flow as a beneficial intermediate step to generate a video sequence conditioned on the initial single frame. A semantic label map is integrated into the flow prediction module to achieve major improvements in the image-to-video generation process. Extensive experiments on the Cityscapes dataset show that our method outperforms all competing methods.

[[paper]](https://arxiv.org/pdf/1903.04480v1.pdf) [[code]](https://github.com/STVIR/seg2vid)



## Framework

**Seg2Img** --> **Img2Vid**

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Seg2Vid/framework.png)

In stage1, a pix2pixHD was utilized to generate images from the corresponding semantic label as the starting frame.

In stage2, the generated image is fed into the network along with a latent vector which models stochasticity to obtain bi-directional flow and occlusion mask. After this, a post-processing U-Net is used to generate the video based on the starting frame and the flow and mask.

The latet vector is sampled from a Gaussian distribution, which is trained with a cVAE in the training stage by reducing the KL divergence of the representation extracted from the video and the Gaussian prior.

![seg2vid](https://github.com/antony0621/Publications-of-Video/blob/master/pics/Seg2Vid/Seg2Vid.png)



## Related Work

Vid2Vid: Semantic label sequence to video sequence



## Loss

Some explanations of its [official implementation](https://github.com/STVIR/seg2vid/blob/junting/src/losses.py).

1. gdloss

   ***TODO***

2. vgg_loss

   Perceptual loss between the vgg feature of the prediction before refinement

3. _quickflowloss

   ![seg2vid](https://github.com/antony0621/Publications-of-Video/blob/master/pics/Seg2Vid/_quickflowloss.png)

   This loss ensures neighborhood pixels (within a 5 x 5 window) to have a similar flow value, but the degree of the punishment is weighted by the image gradient and the distance between the pixels and its reference point. This is similar with bilateral flow filtering that at the edge of the object in an image the value of the pixels changes fast, as well as the image. Thus, in this loss, those pixels with higher image gradient should be given 

4. _flowgradloss

5. imagegradloss

6. SSIM

7. kl_criterion

8. _flowconsist

9. reconlossT



