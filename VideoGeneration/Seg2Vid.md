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

My own explanations of the loss functions its [official implementation](https://github.com/STVIR/seg2vid/blob/junting/src/losses.py).

1. gdloss

   Unclear, maybe same with imagegradloss.

2. vgg_loss

   Perceptual loss between the vgg feature of the prediction before refinement

3. _quickflowloss

   ```python
   def _quickflowloss(self, flow, img, neighbor=5, alpha=1):
       """
       First order neighbor consistenncy prior.
       LK assumption.
       """
       flow = flow * 128
       img = img * 256
       bs, c, h, w = img.size()
       center = int((neighbor - 1) / 2)  
       loss = []
       neighbor_range = list(range(neighbor))
       neighbor_range.remove(center)
       for i in neighbor_range:
           for j in neighbor_range:
               flowsub = (flow[:, :, center:-center, center:-center] -
                          flow[:, :, i:h - (neighbor - i - 1), j:w - (neighbor - j - 1)]) ** 2
               imgsub = (img[:, :, center:-center, center:-center] -
                         img[:, :, i:h - (neighbor - i - 1), j:w - (neighbor - j - 1)]) ** 2 # intensity adaptive weight
               flowsub = flowsub.sum(1)
               imgsub = imgsub.sum(1)
               indexsub = (i - center) ** 2 + (j - center) ** 2  # distance adaptive weight
               loss.append(flowsub * torch.exp(-alpha * imgsub - indexsub))
       return torch.stack(loss).sum() / (bs * w * h)
   ```

   This loss generally ensures neighborhood pixels (within a 5 x 5 window) to have a similar flow value. But it should be noticed that the weights terms, the exponent of the image difference (gradient) and the index difference (distance), give those pixels with more similar in image level and more closer to the reference point (center) higher penalty. Moreover, the exponent is from Eq.3 in [As-Rigid-As-Possible Stereo under Second Order Smoothness Priors](http://vigir.missouri.edu/~gdesouza/Research/Conference_CDs/ECCV_2014/papers/8690/86900112.pdf) and in [MirrorFlow](https://arxiv.org/pdf/1708.05355.pdf), but I have not figured it out why the exponential form is chosen. This whole idea is similar with bilateral filtering, considering both spatial domain and the color (or intensity) domain the same time. Similarly, in [UnFlow](https://arxiv.org/pdf/1711.07837.pdf), the authors utilizes a second-order mutant of this penalty.

   This term may be consistent with Lukas-Kanade assumption.

   

4. _flowgradloss

   Unlike the local _quickflowloss, this loss gives a global constrains to the flow that the adjacent pixels have similar flow, i.e., smothness assumption. Similarly, this loss also weighted by image intensity.

   This term may be consistent with Horn-Schunck assumption.

5. imagegradloss

   This loss ensures the prediction and the ground truth to have closer gradients.

6. Image_similarity

   This loss ensures the prediction and the ground truth to have closer SSIM.

7. kl_criterion

8. _flowconsist

   ```python
   def _flowconsist(self, flow, flowback, mask_fw=None, mask_bw=None):
       if mask_fw is not None:
           # mask_fw, mask_bw = occlusion(flow, flowback, self.flowwarp)
           prevloss = (mask_bw * torch.abs(self.flowwarp(flow, -flowback) - flowback)).mean()
           nextloss = (mask_fw * torch.abs(self.flowwarp(flowback, flow) - flow)).mean()
       else:
           prevloss = torch.abs(self.flowwarp(flow, -flowback) - flowback).mean()
           nextloss = torch.abs(self.flowwarp(flowback, flow) - flow).mean()
       return prevloss + nextloss
   ```

   This is a forward-backward consistency loss, and the mask is to ensure only visible pixels are considered.

   ***TODO***

9. reconlossT



