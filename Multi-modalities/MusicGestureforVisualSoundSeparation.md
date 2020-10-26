# Music Gesture for Visual Sound Separation



## Abstract

Recent deep learning approaches have achieved impressive performance on visual sound separation tasks. However, these approaches are mostly built on appearance and optical flow like motion feature representations, which exhibit limited abilities to find the correlations between audio signals and visual points, especially when separating mul- tiple instruments of the same types, such as multiple violins in a scene. To address this, we propose “Music Gesture,” a keypoint-based structured representation to explicitly model the body and finger movements of musicians when they perform music. We first adopt a context-aware graph network to integrate visual semantic context with body dynamics, and then apply an audio-visual fusion model to associate body movements with the corresponding audio signals. Experimental results on three music performance datasets show: 1) strong improvements upon benchmark metrics for hetero-musical separation tasks (i.e. different instruments); 2) new ability for effective homo-musical separation for piano, flute, and trumpet duets, which to our best knowledge has never been achieved with alternative methods.

[[paper]](https://arxiv.org/pdf/2004.09476.pdf) [[project]](http://music-gesture.csail.mit.edu)



## Method

**A similar architecture with [Sound of Motions](https://github.com/antony0621/Videos-Publications-Collection/blob/master/Multi-modalities/The_Sound_of_Motions.md)**

![framework](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/MusicGestureforVisualSoundSeparation/framework.png)

**Audio-visul Fusion Module**

Different with Sound of Motions, this fusion module is utilized in the audio processing pipeline.

![fusion](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/MusicGestureforVisualSoundSeparation/fusion.png)



## Experiments

**Comparison with [Sound of Motions](https://github.com/antony0621/Videos-Publications-Collection/blob/master/Multi-modalities/The_Sound_of_Motions.md)**

![results](https://github.com/antony0621/Videos-Publications-Collection/blob/master/pics/MusicGestureforVisualSoundSeparation/results.png)



