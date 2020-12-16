# Video Generation From Text



## Abstract

Generating videos from text has proven to be a significant chal- lenge for existing generative models. We tackle this problem by training a conditional generative model to extract both static and dynamic information from text. This is manifested in a hybrid framework, employing a Variational Autoencoder (VAE) and a Generative Adversarial Network (GAN). The static fea- tures, called “gist,” are used to sketch text-conditioned background color and object layout structure. Dynamic features are considered by transforming input text into an image filter. To obtain a large amount of data for training the deep-learning model, we develop a method to automatically create a matched text-video corpus from publicly available online videos. Experimental results show that the proposed framework generates plausible and diverse videos, while accurately reflecting the input text information. It significantly outperforms baseline models that directly adapt text-to-image generation procedures to produce videos. Performance is evaluated both visually and by adapting the inception score used to evaluate image generation in GANs.

[paper](https://arxiv.org/pdf/1710.00421.pdf)



## Structure

**First to 'gist, and then goes to frames'**

![visualization](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/VideoGenerationFromText/visualization.png)

![structure](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/VideoGenerationFromText/structure.png)