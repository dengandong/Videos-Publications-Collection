# Unsupervised Learning of Depth and Ego-Motion from Video



## Abstract

We present an unsupervised learning framework for the task of monocular depth and camera motion estimation from unstructured video sequences. In common with re- cent work, we use an end-to-end learning ap- proach with view synthesis as the supervisory signal. In contrast to the previous work, our method is completely un- supervised, requiring only monocular video sequences for training. Our method uses single-view depth and multi- view pose networks, with a loss based on warping nearby views to the target using the computed depth and pose. The networks are thus coupled by the loss during training, but can be applied independently at test time. Empirical eval- uation on the KITTI dataset demonstrates the effectiveness of our approach: 1) monocular depth performs comparably with supervised methods that use either ground-truth pose or depth for training, and 2) pose estimation performs fa- vorably compared to established SLAM systems under com- parable input settings.

[[paper]](https://people.eecs.berkeley.edu/~tinghuiz/projects/SfMLearner/cvpr17_sfm_final.pdf) [[code]](https://github.com/tinghuiz/SfMLearner)



## Method

**Differentiable Warping Process**

![warping](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SfMLearner/Warping.png)