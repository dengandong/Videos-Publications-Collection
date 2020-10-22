# Learning Correspondence from the Cycle-consistency of Time

It is an oft-told story that when a young graduate student asked Takeo Kanade what are the three most important problems in computer vision, Kanade replied: “***Correspondence, correspondence, correspondence!***”



## Abstract

We introduce a self-supervised method for learning visual correspondence from unlabeled video. The main idea is to use cycle-consistency in time as free supervisory signal for learning visual representations from scratch. At training time, our model learns a feature map representation to be useful for performing cycle-consistent tracking. At test time, we use the acquired representation to find nearest neighbors across space and time. We demonstrate the generalizability of the representation – without finetuning – across a range of visual correspondence tasks, including video object segmentation, keypoint tracking, and optical flow. Our approach outperforms previous self-supervised methods and performs competitively with strongly supervised methods.

[[paper]](https://arxiv.org/pdf/1903.07593.pdf) [[github]](https://ajabri.github.io/timecycle/)



