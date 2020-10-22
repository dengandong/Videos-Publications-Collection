# ADVERSARIAL VIDEO GENERATION ON COMPLEX DATASET



## Introduction



Generative models of natural images have progressed towards high fidelity samples by the strong leveraging of scale. We attempt to carry this success to the field of video modeling by showing that large Generative Adversarial Networks trained on the complex Kinetics-600 dataset are able to produce video samples of substantially higher complexity and fidelity than previous work. Our proposed model, Dual Video Discriminator GAN (DVD-GAN), scales to longer and higher resolution videos by leveraging a computationally efficient decomposition of its discriminator. We evaluate on the related tasks of video synthesis and video prediction, and achieve new state-of-the-art Fréchet Inception Distance for prediction for Kinetics-600, as well as state-of-the-art Inception Score for synthesis on the UCF-101 dataset, alongside establishing a strong baseline for synthesis on Kinetics-600.

[[paper]](https://arxiv.org/pdf/1907.06571.pdf) [[code]](https://github.com/Harrypotterrrr/DVD-GAN)



## Framework

***Generator*** 

* Stacked GRUCell and 2DConvResBlock

***Discriminator (Dual)***

* Spatial Discriminator: Frame Randomly Sampling and 2DConv

* Temporal Discriminator: Dwonsampling and 3DConv

***Basic Structure***

![basic_dvdgan](https://github.com/antony0621/Publications-of-Video/blob/master/pics/DVDGAN/DVDGAN.png)

***Structure for Future Prediction***

![dvdgan_fp](https://github.com/antony0621/Publications-of-Video/blob/master/pics/DVDGAN/DVDGAN_FP.png)



## Loss Function

***Hinge Loss***

Hinge loss of GAN is an extention of Earth Move Distance (EMD), i.e. the loss in [WGAN](https://arxiv.org/pdf/1701.07875.pdf). The hinge loss appears originally in SVM, which is used to push the positive samples and negative samples as far as possible. For the discriminator, the hinge loss reduce the impact on the gradient brought by samples in distant interval, which stabilizes the training procedure.

More details about hinge loss in GAN please go to [Geometric GAN]().

![hinge_loss](https://github.com/antony0621/Publications-of-Video/blob/master/pics/DVDGAN/HingeLoss.png)



## Experiments

***Class-Conditional Video Synthesis***

The input of the generation is a concatenation of a Gaussian prior and the class specific embedding.



***Results on Kinetics-600***

![kinetics600_results](https://github.com/antony0621/Publications-of-Video/blob/master/pics/DVDGAN/Kinetics600_results.png) 

