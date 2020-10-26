# The Sound of Pixels



## Abstract

We introduce PixelPlayer, a system that, by leveraging large amounts of unlabeled videos, learns to locate image regions which produce sounds and separate the input sounds into a set of components that represents the sound from each pixel. Our approach capitalizes on the natural synchronization of the visual and audio modalities to learn models that jointly parse sounds and images, without requiring additional manual supervision. Experimental results on a newly collected MUSIC dataset show that our proposed Mix-and-Separate framework outperforms several baselines on source separation. Qualitative results suggest our model learns to ground sounds in vision, enabling applications such as independently adjusting the volume of sound sources.

[[paper]](https://arxiv.org/pdf/1804.03160.pdf) [[project]](http://sound-of-pixels.csail.mit.edu)



## Method

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SoundofPix/framework.png)

**Mix-and-Separate Moduel, which becomes a standard framework for audio-visual self-supervised learning**

![module](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SoundofPix/module.png)



## Experiments

**Qualitative results on vision-guided source separation on synthetic audio mixtures**

![results](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/SoundofPix/results.png)



