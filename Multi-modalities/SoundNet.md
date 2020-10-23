# SoundNet: Learning Sound Representations from Unlabeled Video



## Abstract

We learn rich natural sound representations by capitalizing on large amounts of unlabeled sound data collected in the wild. We leverage the natural synchronization between vision and sound to learn an acoustic representation using two-million unlabeled videos. Unlabeled video has the advantage that it can be economically acquired at massive scales, yet contains useful signals about natural sound. We propose a student-teacher training procedure which transfers discriminative visual knowledge from well established visual recognition models into the sound modality using unlabeled video as a bridge. Our sound representation yields significant performance improvements over the state-of-the-art results on standard benchmarks for acoustic scene/object classification. Visualizations suggest some high-level semantics automatically emerge in the sound network, even though it is trained without ground truth labels.

[[paper]](http://www.cs.columbia.edu/~vondrick/soundnet.pdf) [[project]](http://projects.csail.mit.edu/soundnet/)



## Framework

This work utilizes visual pre-trained network (e.g. VGG net) to extract the representaion of the video, and minimizes the KL-divergence of the visual presentation and the output of the SoundNet which is used to process the audio track of the corresponding video. In this way, the knowledge is transferred from the visual model to the SoundNet. 



