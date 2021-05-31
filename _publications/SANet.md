---
title: "SANet: A Slice-Aware Network for Pulmonary Nodule Detection"
collection: publications
permalink: /publications/SANet
venue: "IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI)"
date: 2021-03-09
---
<p align="center">
<b>Jie Mei</b><sup>1</sup>, Ming-Ming Cheng<sup>1</sup>, Gang Xu<sup>1</sup>, Lan-Ruo Wan<sup>2</sup>, Huan Zhang<sup>2</sup> <br>
<sup>1</sup>TKLNDST, CS, Nankai University <br>
<sup>2</sup>InferVision
</p>

<p align="center">
  <img src="https://jiemei.xyz/files/2021_TPAMI_SANet/SANet-examples.png?raw=true" alt="Photo" style="width: 450px;"/> <br>
 Figure 1. Examples of the pulmonary nodules in the PN9. 
 Each image belongs to a different class of nodules. SN, GGN, and PSN denote solid, ground-glass, and part-solid nodules, respectively. 
 The size of each nodule is labeled in the parentheses. The 1st and 3rd rows are the complete slices, while the rest two rows are zoomed-in images, respectively.
</p>

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

## Method
<p align="center">
  <img src="https://jiemei.xyz/files/2021_TPAMI_SANet/SANet-method.png?raw=true" alt="Photo" style="max-width:750px"/> <br>
  Figure 2. Overall architecture of the proposed slice-aware network (SANet). The red dashed box represents the nodule candidate. 
  And the CT images below are zoomed-in images of the ones above.
</p>

We propose a slice-aware network (SANet) for pulmonary nodule detection. 
We first introduce an encoder-decoder architecture network to learn the feature of nodules, since their size is much smaller than the common objects in natural images. 
According to doctors’ diagnosis way, we propose a slice grouped non-local module (SGNL) and add it to the encoder network. 
SGNL is able to capture long-range dependencies among any positions and any channels of one slice group in the feature map. 
And 3D region proposal network is introduced to generate pulmonary nodule candidates with high sensitivity, while this detection stage usually comes with many false positives. 
Subsequently, we develop a false positive reduction module (FPR) by using the multi-scale feature maps.

## PN9
We collect and annotate a new large-scale pulmonary nodule
dataset named PN9, which contains 8,798 thoracic CT scans and
a total of 40,439 annotated nodules.

### Dataset Properties
<p align="center">
   <img src="https://jiemei.xyz/files/2021_TPAMI_SANet/SANet-class.png?raw=true" alt="Photo" style="max-width:750px"/> <br>
   Figure 3. Statistics of class in PN9. (a)Taxonomy of the PN9 dataset. 
   It contains four super-classes and nine sub-classes. 
   The percentage represents the proportion of a certain class of nodules to all nodules. 
   (b) Mutual dependencies among super-classes. (c) Mutual dependencies among sub-classes.
</p>

Our PN9 has a hierarchical class structure, and its detailed taxonomy is shown in Fig. 3. 
According to the property of the pulmonary nodules, all nodules in our dataset are first divided into four upper-level classes (denoted as super-class), 
including solid nodule (SN), part-solid nodule (PSN), ground-glass nodule (GGN), and calcific nodule (CN). 
Meanwhile, To satisfy the practical demands of doctors and hospitals, we further subdivide the super-class referring to the medical guidelines. 
Each nodule is assigned with a subordinate class (denoted as sub-class) belonging to a certain super-class based on the nodule size. 
For example, sub-class 0-3mm solid nodules (denoted as 0-3SN) are defined as any nodules identified to be super-class solid nodules with the most significant in-plane dimension in the range of 0-3 mm. And 9 different sub-classes are finally obtained. The statistics of nodules in each class are shown in Fig. 3 (a). 
In Fig. 3 (b-c), we show the mutual dependencies among super-classes and sub-classes, respectively. The larger width of a link between two classes indicates a higher probability for the two classes’ nodules appearing in one patient simultaneously. For example, a patient diagnosed with ground-glass nodules is also likely to have solid nodules.

### Comparison with Other Pulmonary Nodule Datasets
<p align="center">
   <img src="https://jiemei.xyz/files/2021_TPAMI_SANet/SANet-comparison.png?raw=true" alt="Photo" style="max-width:500px"/> <br>
   TABLE 1: Comparison with the existing datasets of the pulmonary nodule. 'Scans' indicates the number of CT scans. 
   ‘Nodules’ denotes the number of labeled nodules. ‘Class' means the class number. And 'Available’ denotes whether the dataset is available.
</p>

In Table 1, we compare the PN9 with several existing pulmonary nodule datasets. 
Compared to the widely used dataset LUNA16, PN9 contains over 10 times more CT scans and over 30 times more annotated nodules. 
As for the class diversity, other datasets only have three categories: nodule >= 3 mm, nodule < 3 mm, and non-nodule. 
Due to these limitations, it is difficult for most of the existing nodule datasets to apply to the practice. 
However, our PN9 contains many CT scans and 9 classes, which will contribute to the detection and classification tasks of the pulmonary nodules, 
allowing researchers to design more effective algorithms based on different types of nodules. 
Besides, there are more pulmonary nodules of small size, like 0-3mm solid nodules and 0-5mm ground-glass nodules. 
It helps identify small nodules more accurately, then the doctors can diagnose and treat patients earlier. 
In summary, our dataset not only is larger than the previous datasets, but also has superior diversity and performance.

## Dataset
SANet: A Slice-Aware Network for Pulmonary Nodule Detection, Jie Mei, Ming-Ming Cheng, Gang Xu, Lan-Ruo Wan, Huan Zhang, IEEE TPAMI, 2021. 
[[PDF]](https://jiemei.xyz/files/2021_TPAMI_SANet/2021_TPAMI_SANet.pdf)[[Code]](https://github.com/mj129/SANet)

Please contact Jie Mei (meijie AT mail.nankai.edu.cn) for the dataset. 
We will get back to you shortly.<br>
The email should contain the following information.
```
Name: (Tell us who you are.)
Affiliation: (The name/url of your institution or university, etc.)
Job Title: (E.g., Professor, Associate Professor, PhD, etc.)
Email: (Dataset will be sent to this email. 
Note: For better academic communication, a real-name system is encouraged and your email suffix must match your affiliation (e.g., hello@nankai.edu.cn).)
```


### Terms of Use
This dataset belongs to the Media Computing Lab at Nankai University and is licensed under a [Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode).

### Citation
It would be high appreciated if you can cite our paper when using our dataset and code:
```
@article{21PAMI-SANet,
  title={SANet: A Slice-Aware Network for Pulmonary Nodule Detection},
  author={Jie Mei and Ming-Ming Cheng and Gang Xu and Lan-Ruo Wan and Huan Zhang},
  journal={IEEE transactions on pattern analysis and machine intelligence},
  year={2021},
  publisher={IEEE},
  doi={10.1109/TPAMI.2021.3065086}
}
```