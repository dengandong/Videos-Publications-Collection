# The Sound of Motions



## Abstract

Sounds originate from object motions and vibrations of surrounding air. Inspired by the fact that humans is capable of interpreting sound sources from how objects move visu- ally, we propose a novel system that explicitly captures such motion cues for the task of sound localization and separa- tion. Our system is composed of an end-to-end learnable model called Deep Dense Trajectory (DDT), and a curricu- lum learning scheme. It exploits the inherent coherence of audio-visual signals from a large quantities of unlabeled videos. Quantitative and qualitative evaluations show that comparing to previous models that rely on visual appear- ance cues, our motion based system improves performance in separating musical instrument sounds. Furthermore, it separates sound components from duets of the same cat- egory of instruments, a challenging problem that has not been addressed before.

[[papers]](https://arxiv.org/pdf/1904.05979.pdf) [[demo]](http://people.csail.mit.edu/hangzhao/videos/SoM_supp.mp4) 



## Framework

The framework is consist of four components: a **motion network**, an **appearance network**, a **fusion module**, and a **sound separation network**. The motion network takes a sequence of frames and outputs trajectory features; appearance network takes the first video frame and outputs appearance features; fusion module fuses appearance and trajectory features; sound separation network separates the input audio conditioned on the visual features.

![framework]()