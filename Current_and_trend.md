# 知识蒸馏当下理论进展和研究方向

## 2015

知识蒸馏的概念首次于2015年提出： Distilling the Knowledge in a neural network文章，其动机是因为用复杂的模型来做预测太消耗计算资源，导致模型难以部署，因此作者的团队发现把一个复杂模型的知识压缩到一个简单模型是可行的，并在mnist和语音识别数据集上做了测试，证明了其可行性。并定义了知识，和超参数-蒸馏温度T，提出蒸馏公式!()[https://github.com/Zxl19990529/Knowledge_Distrillation/blob/master/Images/gongshi.png]

## 2016

2016年 [Net2Net:ACCELERATING LEARNING VIA KNOWLEDGE TRANSFER](https://arxiv.org/pdf/1511.05641.pdf) 提出了知识迁移的概念，来解决大型网络训练速度慢的问题，但并不是知识蒸馏，而是知识迁移。例如先训练一个小的网络，然后用Net2Net利用小网络的已经训练好的权重训练一个大网络。其中用小网络权重的过程就是知识迁移过程。为了实现知识迁移文章定义了2个操作：Net2WiderNet和Net2DeeperNet，但这两个操作有一定局限性，在全连接层和卷基层上可以用这两个操作实现Net to Net,从而实现加速大网络的训练。

## 2017

- 知识蒸馏的理论被应用到人脸识别上（AAAI）： [Face model compression by distilling knowledge from neurons](http://www.aaai.org/ocs/index.php/AAAI/AAAI16/paper/download/11977/12130)
by Distilling Knowledge from Neurons，文章以（保证人脸识别技术精度的同时欲将人脸识别迁移至移动端与嵌入式设备中）为动力，用知识蒸馏的手段来实现。其方法为：使用teacher网络的最高隐藏层的输出作为“知识”，监督student网络训练。

- ICLR会议论文：[PAYING MORE ATTENTION TO ATTENTION: IMPROVING THE PERFORMANCE OF CONVOLUTIONAL NEURAL NETWORKS VIA ATTENTION TRANSFER](https://arxiv.org/pdf/1612.03928.pdf)
利用和知识蒸馏类似思想，用Teacher-Student 网络实现了”卷积神经网络的注意力“的蒸馏转移。 并只有0.5的精度损失。

- NIPS论文：[Learning Efficient Object Detection Models with Knowledge Distillation](https://papers.nips.cc/paper/6676-learning-efficient-object-detection-models-with-knowledge-distillation.pdf) 提出了更紧凑的目标检测网络结构（FItNets15和新的loss），并针对标签少、不平衡的数据，结合知识蒸馏的手段提升了目标检测的准确率。

- CVPR论文：[A Gift from Knowledge Distillation: Fast Optimization, Network Minimization and Transfer Learning](http://openaccess.thecvf.com/content_cvpr_2017/papers/Yim_A_Gift_From_CVPR_2017_paper.pdf) 提出了有效的知识迁移手段，并达到一下效果：（1）student网络算的比teacher网络快（2）student网络准确度更高（3）对不同的teacher网络，student网络都可以有效的学习到知识。

## 2018  

- ICLR论文：[Large scale distributed neural network training through online distillation](https://openreview.net/pdf?id=rkr1UDeC-) ， 针对分布式SGD存在的瓶颈，提出在线蒸馏方法提高大规模计算集群上的模型表现和计算效率。

- ICML论文：[Born-Again Neural Networks](https://arxiv.org/pdf/1805.04770.pdf)（再生神经网络）重新审视了知识蒸馏，但侧重点与以往不同，不再是模型压缩，而转变为把知识从教师模型迁移给具有相同能力的学生模型，并惊奇的发现学生模型通过再生树策略明显超过教师模型，而且弱的教师模型依然可以提升学生模型的准确率。

## 从部署模式的角度对当前网络模型的分类

- 当前针对服务器端的高性能网络：
    - VGGNet:
    - ResNet:
    - InceptionNet:
    - DenseNet:
    - Inside-OutsideNet:
    - SE-Net:
- 针对移动端部署的网络：
    - MobileNet:
    - ShuffleNet:
    - ShuffleNet V2:
    - MobileFaceNets: