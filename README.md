# Deep-CSC-Networks-For-Image-Fusion
Deep Convolutional Sparse Coding Networks for Image Fusion. [arxiv](https://arxiv.org/abs/2005.08448)

[Shuang Xu *](https://xsxjtu.github.io/), [Zixiang Zhao *](https://www.researchgate.net/profile/Zixiang_Zhao5/), [Yicheng Wang](https://www.researchgate.net/profile/Wang_Yicheng4), Kai Sun, [Chunxia Zhang](https://www.researchgate.net/profile/Chun_Xia_Zhang/), [Junmin Liu](http://gr.xjtu.edu.cn/web/junminliu/), [Jiangshe Zhang](http://gr.xjtu.edu.cn/web/jszhang/). (* equal contributions)

## Abstract
Image fusion is a significant problem in many fields including digital photography, computational imaging and remote sensing, to name but a few. Recently, deep learning has emerged as an important tool for image fusion. This paper presents three deep convolutional sparse coding (CSC) networks for three kinds of image fusion tasks (i.e., infrared and visible image fusion, multi-exposure image fusion, and multi-modal image fusion), where the CSC model and the iterative shrinkage and thresholding algorithm are generalized into dictionary convolution units. As a result, all hyper-parameters in the CSC model are learned from data. Our extensive experiments and comprehensive comparisons reveal the superiority of the proposed networks with regard to quantitative evaluation and visual inspection.

## CSC Unfolding
The CSC optimizes the following problem,
![avatar](https://latex.codecogs.com/gif.download?%5Cmin_%7B%5Cboldsymbol%20z%7D%5Cfrac%7B1%7D%7B2%7D%5C%7C%5Cboldsymbol%7Bx%7D-%5Cboldsymbol%7Bd%7D*%5Cboldsymbol%7Bz%7D%5C%7C_2%5E2+%5Clambda%20g%28%5Cboldsymbol%7Bz%7D%29)
## Network Structure
![avatar](image/Net_v3_copy.png)
