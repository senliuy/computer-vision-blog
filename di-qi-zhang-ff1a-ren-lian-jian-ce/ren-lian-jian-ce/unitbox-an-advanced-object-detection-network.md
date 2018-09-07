# UnitBox: An Advanced Object Detection Network

## 前言

UnitBox使用了和[DenseBox](https://senliuy.gitbooks.io/advanced-deep-learning/content/di-qi-zhang-ff1a-ren-lian-jian-ce/ren-lian-jian-ce/densebox-unifying-landmark-localization-with-end-to-end-object-detection.html)\[2\]类似的基于图像分割的方法进行人脸检测。在DenseBox中，bounding box的定位使用的是l2损失。l2损失的一个缺点是会使模型在训练过程中更偏向于尺寸更大的物体，因为大尺寸物体的l2损失更容易大于小物体。

为了解决这个问题，UnitBox中使用了IoU损失，顾名思义，IoU损失既是使用Ground Truth和预测bounding box的交并比作为损失函数。

## 1. UnitBox详解

首先回顾DenseBox中介绍的几个重要的知识点，明白了这些知识点才能理解下面要讲解的UnitBox。这里声明，为了和DenseBox的l2损失做对比，我们放弃了论文中使用的变量名，而是采用DenseBox中的变量名。



1. DenseBox网络结构是全卷积网络，输出层是一个$$\frac{m}{4}\times \frac{n}{4}$$的Feature Map，是一个image-to-image的任务；
2. 输出Feature Map的每个像素点$$(x_i, y_i)$$都是可以确定一个检测框的样本，包样本含置信度$$y$$和该点到bounding box四条边的距离$$(d_{x^t},d_{x^b},d_{y^t},d_{y^b})$$，如[DenseBox解析](https://senliuy.gitbooks.io/advanced-deep-learning/content/di-qi-zhang-ff1a-ren-lian-jian-ce/ren-lian-jian-ce/densebox-unifying-landmark-localization-with-end-to-end-object-detection.html)中的图2。

### 1.1 UnitBox的前向计算 



## Reference

\[1\]Zhou X, Yao C, Wen H, et al. EAST: an efficient and accurate scene text detector\[C\]//Proc. CVPR. 2017: 2642-2651.

\[2\] Qin H, Yan J, Li X, et al. Joint training of cascaded cnn for face detection\[C\]//Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2016: 3456-3465.
