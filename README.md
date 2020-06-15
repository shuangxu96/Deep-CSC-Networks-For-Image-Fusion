# Deep-CSC-Networks-For-Image-Fusion
Deep Convolutional Sparse Coding Networks for Image Fusion. [arxiv](https://arxiv.org/abs/2005.08448)

[Shuang Xu *](https://xsxjtu.github.io/), [Zixiang Zhao *](https://www.researchgate.net/profile/Zixiang_Zhao5/), [Yicheng Wang](https://www.researchgate.net/profile/Wang_Yicheng4), Kai Sun, [Chunxia Zhang](https://www.researchgate.net/profile/Chun_Xia_Zhang/), [Junmin Liu](http://gr.xjtu.edu.cn/web/junminliu/), [Jiangshe Zhang](http://gr.xjtu.edu.cn/web/jszhang/). (* equal contributions)

## Abstract
Image fusion is a significant problem in many fields including digital photography, computational imaging and remote sensing, to name but a few. Recently, deep learning has emerged as an important tool for image fusion. This paper presents three deep convolutional sparse coding (CSC) networks for three kinds of image fusion tasks (i.e., infrared and visible image fusion, multi-exposure image fusion, and multi-modal image fusion), where the CSC model and the iterative shrinkage and thresholding algorithm are generalized into dictionary convolution units. As a result, all hyper-parameters in the CSC model are learned from data. Our extensive experiments and comprehensive comparisons reveal the superiority of the proposed networks with regard to quantitative evaluation and visual inspection.

## CSC Unfolding
The CSC optimizes the following problem,

<a href="https://www.codecogs.com/eqnedit.php?latex=\min_{\boldsymbol&space;z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2&plus;\lambda&space;g(\boldsymbol{z})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\min_{\boldsymbol&space;z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2&plus;\lambda&space;g(\boldsymbol{z})." title="\min_{\boldsymbol z}\frac{1}{2}\|\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}\|_2^2+\lambda g(\boldsymbol{z})" /></a>

where <a href="https://www.codecogs.com/eqnedit.php?latex=\lambda" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\lambda" title="\lambda" /></a> is a hyperparameter, * denotes the convolution operator, <a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{z}\in&space;R^{q\times&space;h&space;\times&space;w}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{z}\in&space;R^{q\times&space;h&space;\times&space;w}" title="\boldsymbol{z}\in R^{q\times h \times w}" /></a> is the sparse feature map (or say, code) and <a href="https://www.codecogs.com/eqnedit.php?latex=g(\cdot)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?g(\cdot)" title="g(\cdot)" /></a> is a sparse regularizer. This problem can be solved by ISTA, and its updating rule is as below,

<a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{z}^{(k&plus;1)}&space;\leftarrow&space;\mathrm{prox}_{\lambda/\rho}\left(\boldsymbol{z}^{(k)}&plus;\frac{1}{\rho}\boldsymbol{d}^T*(\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}^{(k)})\right)." target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{z}^{(k&plus;1)}&space;\leftarrow&space;\mathrm{prox}_{\lambda/\rho}\left(\boldsymbol{z}^{(k)}&plus;\frac{1}{\rho}\boldsymbol{d}^T*(\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}^{(k)})\right)" title="\boldsymbol{z}^{(k+1)} \leftarrow \mathrm{prox}_{\lambda/\rho}\left(\boldsymbol{z}^{(k)}+\frac{1}{\rho}\boldsymbol{d}^T*(\boldsymbol{x}-\boldsymbol{d}*\boldsymbol{z}^{(k)})\right)" /></a>

We replace some operations with deep neural networks' elements and rewritten the updating rule, that is, 

<a href="https://www.codecogs.com/eqnedit.php?latex=\boldsymbol{z}^{(k&plus;1)}&space;=&space;f\left(&space;{\rm&space;BN}\left(&space;\boldsymbol{z}^{(k)}&plus;\mathrm{Conv}_1(\boldsymbol{x}-\mathrm{Conv}_0(\boldsymbol{z}^{(k)}))&space;\right)&space;\right)." target="_blank"><img src="https://latex.codecogs.com/gif.latex?\boldsymbol{z}^{(k&plus;1)}&space;=&space;f\left(&space;{\rm&space;BN}\left(&space;\boldsymbol{z}^{(k)}&plus;\mathrm{Conv}_1(\boldsymbol{x}-\mathrm{Conv}_0(\boldsymbol{z}^{(k)}))&space;\right)&space;\right)." title="\boldsymbol{z}^{(k+1)} = f\left( {\rm BN}\left( \boldsymbol{z}^{(k)}+\mathrm{Conv}_1(\boldsymbol{x}-\mathrm{Conv}_0(\boldsymbol{z}^{(k)})) \right) \right)." /></a>

The above equation is called as the dictnary convolutional unit (DCU).

## Network Structure
![avatar](image/Net_v3_copy.png)
