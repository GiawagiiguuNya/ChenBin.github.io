---
title: Few-shot adaptive gaze estimation 
tags: Gaze_Recognition paper
---

#  _Few-shot adaptive gaze estimation_

> Park, Seonwook, et al. "Few-shot adaptive gaze estimation." Proceedings of the IEEE/CVF International Conference on Computer Vision. 2019.

This is a popular method, and it rank the first on the MPIIGaze.
it based on two methods: Disentangling Transforming Encoder-Decoder for representation learning and MAML meta learning for a adaptable gaze estimation network. 



__The FAZE frame__:

![FAZE_overview](/GazeRecognition/FAZE/FAZE_overview.png)



__Representation learning__:
aim to build a feature extractor.

![Representation Learning1](/GazeRecognition/FAZE/RepresentationLearning.png)

as showed in the image, they code and  decode within 25 degrees.

![Representation Learning2](/GazeRecognition/FAZE/RepresentationLearning2.png)

latent space consists of three parts: Appearance code(pass through, maybe re-cognition),Gaze direction code and Head rotation code. this part will be trained by pairs of image of the same person. Similar like: find the parameters that can change the gaze direction and head pose (Appearance code used to recognize the same person).
The result is good? --> use three Loss function to show.


$$
L_{full} = λ_{recon}L_{recon} + λ_{EC}L_{EC} + λ_{gaze}L_{gaze}
$$

__Adaptable gaze estimation network__:
aim to compute a good enough preset weight value so that the network can converge within few  frames for a specific person (different eye construction).

converge the system:
DT-ED+fine_turning, DT-ED+MAML, FAZE. -> A good preset weight value is necessary.



__In Ablation Study section__:
The authors point out that the two parts of the system are all necessary.



__Appendix__:

https://github.com/NVlabs/few_shot_gaze
https://paperswithcode.com/dataset/mpiigaze

11:30
[https://www.youtube.com/watch?v=ByfFufRhuRc&t=688s]

Few-shot learning is to know the similarity and difference between objects.  ->   Generate a similarity function

<!--more-->
