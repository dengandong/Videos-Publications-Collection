# Spatio-temporal Video Autoencoder with Differentiable Memory



# Abstract

We describe a new spatio-temporal video autoencoder, based on a classic spatial image autoencoder and a novel nested temporal autoencoder. The temporal encoder is represented by a differentiable visual memory composed of convolutional long short-term memory (LSTM) cells that integrate changes over time. Here we target motion changes and use as temporal decoder a robust optical flow prediction module together with an image sampler serving as built-in feedback loop. The ar- chitecture is end-to-end differentiable. At each time step, the system receives as input a video frame, predicts the optical flow based on the current observation and the LSTM memory state as a dense transformation map, and applies it to the current frame to generate the next frame. By minimising the reconstruction error between the predicted next frame and the corresponding ground truth next frame, we train the whole system to extract features useful for motion estimation without any supervision effort. We present one direct application of the proposed framework in weakly-supervised semantic segmentation of videos through label propagation using optical flow.

[[paper]](http://de.arxiv.org/pdf/1511.06309) 



## Framework

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Spatio-temporalAE/framework.png)

**LSTM Memory**

A similar structure with [ConvLSTM](https://arxiv.org/pdf/1506.04214.pdf).

**Optical Flow Predictor**

Large kernel size: Large kernels are needed since the magnitude of the predicted optical flow is limited by the size of the filters.

**Huber Penalty**

![huber](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Spatio-temporalAE/huber.png)

**Grid Generator and Image Sampler**

![gg&sampler](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Spatio-temporalAE/sampler.png)



## Experiments

**Warping Performance by Grid Generator and Sampler**

Warping performed by the GG and S modules, given a video frame and the ground truth optical flow map. First line: input frame and ground truth optical flow map displayed using the colour code shown in the top-right corner of the image; the colour encodes the direction of movement and the colour intensity reflects the magnitude; darker shades correspond to higher magnitudes. Second line: ground truth next frame and sampled next frame; note the artifacts close to the boundaries.

![warping](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Spatio-temporalAE/warping_per.png)



**Results on Moving MNIST**

![MNIST](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/Spatio-temporalAE/moving_digits.png)











