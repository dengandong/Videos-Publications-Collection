# Self-supervised Moving Vehicle Tracking with Stereo Sound



## Abstract

Humans are able to localize objects in the environment using both visual and auditory cues, integrating information from multiple modalities into a common reference frame. We introduce a system that can leverage unlabeled audiovi- sual data to learn to localize objects (moving vehicles) in a visual reference frame, purely using stereo sound at infer- ence time. Since it is labor-intensive to manually annotate the correspondences between audio and object bounding boxes, we achieve this goal by using the co-occurrence of vi- sual and audio streams in unlabeled videos as a form of self- supervision, without resorting to the collection of ground truth annotations. In particular, we propose a framework that consists of a vision “teacher” network and a stereo- sound “student” network. During training, knowledge em- bodied in a well-established visual vehicle detection model is transferred to the audio domain using unlabeled videos as a bridge. At test time, the stereo-sound student network can work independently to perform object localization us- ing just stereo audio and camera meta-data, without any visual input. Experimental results on a newly collected Au- ditory Vehicle Tracking dataset verify that our proposed ap- proach outperforms several baseline approaches. We also demonstrate that our cross-modal auditory localization ap- proach can assist in the visual localization of moving vehi- cles under poor lighting conditions.

[[paper]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Gan_Self-Supervised_Moving_Vehicle_Tracking_With_Stereo_Sound_ICCV_2019_paper.pdf)



## Framework

Paradigm: Teacher-sturent training.

Visual branch: Pre-trained YOLOv2

Auditory branch: StereoSoundNet trained from scratch

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SelfSupMovingVehicleTrackingwithStereoSound/framework.png)



## Loss

**Feature alignment loss**

Following [See, Hear, and Read: Deep Aligned Representations](http://people.csail.mit.edu/yusuf/see-hear-read/paper.pdf), ranking loss is leveraged to constrain the features in different subnetworks at same level.

![loss1](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SelfSupMovingVehicleTrackingwithStereoSound/loss1.png)

In which, 

![loss_phi](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SelfSupMovingVehicleTrackingwithStereoSound/loss_phi.png)



