# TwoStreamVAN: Improving Motion Modeling in Video Generation



## Abstract

Video generation is an inherently challenging task, as it requires modeling realistic temporal dynamics as well as spatial content. Existing methods entangle the two intrinsically different tasks of motion and content creation in a single generator network, but this approach struggles to simultaneously generate plausible motion and content. To improve motion modeling in video generation task, we propose a two stream model that disentangles motion generation from content generation, called a Two-Stream Variational Adversarial Network (TwoStreamVAN). Given an action label and a noise vector, our model is able to create clear and consistent motion, and thus yields photorealistic videos. The key idea is to progressively generate and fuse multi-scale motion with its corresponding spatial content. Our model significantly outperforms existing methods on the standard Weizmann Human Action, MUG Facial Expression and VoxCeleb datasets, as well as our new dataset of diverse human actions with challenging and complex motion.

[[paper]](https://arxiv.org/pdf/1812.01037v2.pdf) [[code]](https://github.com/sunxm2357/TwoStreamVAN/)



## Framework

Different from other works, the author encode the difference between two frames to obtain motion code.

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/TwoStreamVAN/framework.png)

The motion and content are fused together at each layer of the generator via a gated mechanism.

![fusion](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/TwoStreamVAN/fusion.png)



***TODO***

