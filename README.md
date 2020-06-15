# Deep-CSC-Networks-For-Image-Fusion
Deep Convolutional Sparse Coding Networks for Image Fusion. [arxiv](https://arxiv.org/abs/2005.08448)

[Shuang Xu *](https://xsxjtu.github.io/), [Zixiang Zhao *](https://www.researchgate.net/profile/Zixiang_Zhao5/), [Yicheng Wang](https://www.researchgate.net/profile/Wang_Yicheng4), Kai Sun, [Chunxia Zhang](https://www.researchgate.net/profile/Chun_Xia_Zhang/), [Junmin Liu](http://gr.xjtu.edu.cn/web/junminliu/), [Jiangshe Zhang](http://gr.xjtu.edu.cn/web/jszhang/). (* equal contributions)

## Abstract
Image fusion is a significant problem in many fields including digital photography, computational imaging and remote sensing, to name but a few. Recently, deep learning has emerged as an important tool for image fusion. This paper presents three deep convolutional sparse coding (CSC) networks for three kinds of image fusion tasks (i.e., infrared and visible image fusion, multi-exposure image fusion, and multi-modal image fusion), where the CSC model and the iterative shrinkage and thresholding algorithm are generalized into dictionary convolution units. As a result, all hyper-parameters in the CSC model are learned from data. Our extensive experiments and comprehensive comparisons reveal the superiority of the proposed networks with regard to quantitative evaluation and visual inspection.

## CSC Unfolding
The CSC optimizes the following problem,

<a href="https://www.codecogs.com/eqnedit.php?latex=\min_{\boldsymbol&space;z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2&plus;\lambda&space;g(\boldsymbol{z})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\min_{\boldsymbol&space;z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2&plus;\lambda&space;g(\boldsymbol{z})." title="\min_{\boldsymbol z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2+\lambda g(\boldsymbol{z})" /></a>

where <a href="https://www.codecogs.com/eqnedit.php?latex=\lambda" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\lambda" title="\lambda" /></a> is a hyperparameter, * denotes the convolution operator, <a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{z}\in&space;R^{q\times&space;h&space;\times&space;w}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{z}\in&space;R^{q\times&space;h&space;\times&space;w}" title="\boldsymbol{z}\in R^{q\times h \times w}" /></a> is the sparse feature map (or say, code) and <a href="https://www.codecogs.com/eqnedit.php?latex=g(\cdot)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?g(\cdot)" title="g(\cdot)" /></a> is a sparse regularizer.
## Network Structure
![avatar](image/Net_v3_copy.png)
