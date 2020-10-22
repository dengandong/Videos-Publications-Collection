# Video Textures



## Abstract

This paper introduces a new type of medium, called a video texture, which has qualities somewhere between those of a photograph and a video. A video texture provides a continuous infinitely varying stream of images. While the individual frames of a video texture may be repeated from time to time, the video sequence as a whole is never repeated exactly. Video textures can be used in place of digital photos to **infuse a static image with dynamic qualities and explicit action**. We present techniques for analyzing a video clip to extract its structure, and for **synthesizing a new, similar looking video** of arbitrary length. We combine video textures with view morphing techniques to obtain 3D video textures. We also introduce video-based animation, in which the synthesis of video textures can be guided by a user through high-level interactive controls. Applications of video textures and their extensions include the display of dynamic scenes on web pages, the creation of dynamic backdrops for special effects and games, and the interactive control of video-based animation.

[[paper]](http://szeliski.org/papers/Schodl-SG2000.pdf)



## Application Scenario

* Computer games in dynamic backdrops or foreground synthesis

* Combined with stereo matching and view morphing to produce 3D video textures that can be rendered from continually varying viewpoints

* Video-based animation: high level interactive control in real time, e.g., changing the speed of a moving object in a source video, or removing or adding video textures in the middle to shorten or lengthen the source video.



## Challenges

* Locating potential transition points in the video sequences, i.e., places where the video can be looped back on itself in a minimally obtrusive way
* Finding a sequence of transitions that respects the global structure of the video
* Smoothing visual discontinuities at the transitions (could be solved by morphing techniques)
* Automatically factoring video frames into different regions that can be analyzed and synthesized independently
* Others: creating good, fixed-length cycles; separating video texture elements from their backgrounds so that they can be used as video sprites; applying view morphing tovideo imagery; and generalizing the transition metrics to incorporate real-time user input.



## Related Work

Video textures can be viewed as a kind of "video-based rendering" or an extension of 2D image texture synthesis.

* Video Rewrite: reorder a sequence of a dynamic object, often a speaking mouth, to match a new audio track. More details at: [Video rewrite: Driving visual speech with audio](http://www.mit.edu/~9.520/spring09/Papers/VideoRewrite.pdf).
* Video Sprite: More details at: [View Synthesis by Trinocular Edge Matching and Transfer](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.41.1098&rep=rep1&type=pdf)
* Video Clip-Art
* *TODO*



## Methods

Find places in the original video where a transition can be made to some other place in the video clip without introducing noticeable discontinuities.

![system](https://github.com/antony0621/Publications-of-Video/blob/master/pics/VideoTextures/system.png)

![pendulum](https://github.com/antony0621/Publications-of-Video/blob/master/pics/VideoTextures/pendulum.png)

