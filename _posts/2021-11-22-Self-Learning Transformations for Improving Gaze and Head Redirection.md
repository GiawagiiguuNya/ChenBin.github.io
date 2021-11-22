title: Self-Learning Transformations for Improving Gaze and Head Redirection
tags: Gaze_Recognition paper

------------



# Self-Learning Transformations for Improving Gaze and Head Redirection

provide us a new way to build a feature extraction based on GAN.

compared to the method used in the  *Few-shot adaptive gaze recognition*, this method can deal with unrelated factor based on using Innovative label vector.

![ST-ED](\GazeRecognition\ST-ED\ST-ED.png)

**the problem setting:** To train a conditional generative network which can complete the following project: 
$$
(X_{i}, \bf{c_{t}}) \rightarrow X_{t}
$$
use pairs of image of the same person.

**image representation:** personal non-varying embedding (appearance) + N factors of image variations 
$$
z_{i}^0  \\
\mathbf{f_{i}} =\{f^1_{i},f^2_{i},f^3_{i}...f^N_{i}\} \\
in \space which: \space \space \space \space \space 
f^j_{i} \gets c_i^{j},z_i^{j} \\
for \space simple: \space 
(z_{i}^0,c_i^{1},z_i^{1},c_i^{2},z_i^{2},...,c_i^{N},z_i^{N})\\
$$
 overall image condition of $X_i $
$$
\mathbf{c_i} =\{c_i^{1},c_i^{2},c_i^{3},...,c_i^{N}\}
$$
and a important assumption: subset $c_i $ of factors are extraneous to the task and are **unknown** **a** **priori**.

-> a new architecture based on **transforming encoder-decoders**. Extend T-ED to discover, encode and **disentangle multiple extraneous unknown factors in a self-supervised manner.**



**the most difference lay on**:

For a pair of images $X_i $ and $X_t $, ST-ED predicts their personal non-varying codes (z^0_i and z^0_t ), their pseudo-label conditions ($ \tilde{c}_i$ and $\tilde{c }_t$) and embedding representations (z_i and z_t)

**The pipeline:**
$$
\{z_{i}^0,\{z_{i}^1,\tilde{c}_i^1\},\{z_{i}^2,\tilde{c}_i^2\},...,\{z_{i}^N,\tilde{c}_i^N\}\} \gets G_{enc}(X_i) \\
\{z_{t}^0,\{z_{t}^1,\tilde{c}_i^1\},\{z_{t}^2,\tilde{c}_i^2\},...,\{z_{t}^N,\tilde{c}_i^N\}\} \gets G_{enc}(X_t)
\\
\\
\tilde{z}_t^j = T({z}_i^j,\tilde{c}_i^j,\tilde{c}_t^j) = \mathbf{R}_t^j(\mathbf{R}_i^j)^{-1}z_i^j, \space \space \space j \in \{1,2,3...,N\}
\\
\mathbf{\tilde{X}_t} =G_{dec}(\mathbf{\tilde{z}_t})
$$

1. calculate the representation of input image and output image.

2. rotate the presentation according to the conditions.

3. decode it 

Appendix:

> Zheng, Yufeng, et al. "Self-Learning Transformations for Improving Gaze and Head Redirection." *arXiv preprint arXiv:2010.12307* (2020).

