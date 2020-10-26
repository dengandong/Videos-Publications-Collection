# SfM-Net: Learning of Structure and Motion from Video



## Abstract

We propose SfM-Net, a geometry-aware neural network for motion estimation in videos that decomposes frame- to-frame pixel motion in terms of scene and object depth, camera motion and 3D object rotations and translations. Given a sequence of frames, SfM-Net predicts depth, seg- mentation, camera and rigid object motions, converts those into a dense frame-to-frame motion field (optical flow), differentiably warps frames in time to match pixels and back-propagates. The model can be trained with vari- ous degrees of supervision: 1) self-supervised by the re- projection photometric error (completely unsupervised), 2) supervised by ego-motion (camera motion), or 3) super- vised by depth (e.g., as provided by RGBD sensors). SfM- Net extracts meaningful depth estimates and successfully estimates frame-to-frame camera rotations and transla- tions. It often successfully segments the moving objects in the scene, even though such supervision is never provided.

[[paper]](https://arxiv.org/pdf/1704.07804.pdf)



## Framework

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SfM-Net/framework.png)

![structure](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SfM-Net/structure.png)

