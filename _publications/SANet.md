---
title: "SANet: A Slice-Aware Network for Pulmonary Nodule Detection"
collection: publications
permalink: /publications/SANet
venue: "IEEE Transactions on Pattern Analysis and Machine Intelligence (**TPAMI**)"
date: 2021
---

[[PDF]](https://jiemei.xyz/files/2021_TPAMI_SANet/2021_TPAMI_SANet.pdf)

## Abstract
Lung cancer is the most common cause of cancer death worldwide. 
A timely diagnosis of the pulmonary nodules makes it possible to detect lung cancer in the early stage, 
and thoracic computed tomography (CT) provides a convenient way to diagnose nodules. 
However, it is hard even for experienced doctors to distinguish them from the massive CT slices. 
The currently existing nodule datasets are limited in both scale and category, 
which is insufficient and greatly restricts its applications. 
In this paper, we collect the largest and most diverse dataset named PN9 for pulmonary nodule detection by far. 
Specifically, it contains 8,798 CT scans and 40,439 annotated nodules from 9 common classes. 
We further propose a slice-aware network (SANet) for pulmonary nodule detection. 
A slice grouped non-local (SGNL) module is developed to capture long-range dependencies among any positions and any channels of one slice group in the feature map. 
And we introduce a 3D region proposal network to generate pulmonary nodule candidates with high sensitivity, while this detection stage usually comes with many false positives. 
Subsequently, a false positive reduction module (FPR) is proposed by using the multi-scale feature maps. 
To verify the performance of SANet and the significance of PN9, 
we perform extensive experiments compared with several state-of-the-art 2D CNN-based and 3D CNN-based detection methods. 
Promising evaluation results on PN9 prove the effectiveness of our proposed SANet.