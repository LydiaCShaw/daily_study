---
layout: post
read_time: true
show_date: true
title: Some methods of recognition of scoliosis
date:   2021-07-14 21:32:20 -0600
description: Record some articles that use different methods to recognition spine
img: posts/stock/11.jpg
tags: [AIS,scoliosis,coding,recognition,vertebrae segmetation]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
## BoostNet

iSpine proposed a method based on X-rays film in which the S2VR was validated on a dataset composed of 439 samples from various subjects and BoostNet validation was conducted on a dataset consisting of 481 spinal anterior-posterior x-ray images. The approach called BoostNet that performs direct spinal landmark estimation to achieve fully automatic clinical Adolescent Idiopathic Scoliosis assessment.

①BoostNet automatically and efficiently locates spinal landmarks to provide a multi-purpose framework for robust quantitative assessment of spinal curvatures.

②Efficiently eliminates deleterious effects of outlier features to improve robustness and generalizability.

③Improves regression accuracy using a spinal structured multi-ouput layer.

④Explicitly enforces dependencies between each spinal landmark to alleviate the impact of small datasets.
### Structured Support Vector Regression (S2VR)
ISpine proposed the S2VR to directly predict the Cobb angles and landmarks of the spine from spinal X-ray images.

S2VR performs nonlinear mapping and explicit correlation modeling in a single framework.
Nonlinear mapping handles the relationship between the input images and high-level outputs (angles and landmarks).
Correlation modelling captures the correlations among outputs.
Formulates the prediction as a multi-output regression task.
Kernel target alignment is used to improve performance by increasing the discriminative ability of the kernels.
### Approach
The proposed framework extracts image features from spinal X-ray images and outputs coordinates, angles, and landmarks. The regression task predicts the coordinates and Cobb angles from the given input image features.
![image1](.\assets\img\posts\20210714\ispine1.png)
*figure shown the framework of the structured support vector regression (S2VR)*

![image2](.\assets\img\posts\20210714\ispine2.png)
*figure shown the method overcomes huge variations and high ambiguities and achieves high accuracy in landmark detection*

### BoostNet 
The BoostNet framework consists of three parts:

①Series of convolutional layers to perform automated feature extraction.

②Newly designed BoostLayer to remove deleterious outlier features.

③Spinal structured multi-output layer to alleviate the impact of small datasets.
![image3](.\assets\img\posts\20210714\ispine3.png)
*figure shown architecture of the BoostNet for landmark based AIS assessment. Relevant features are automatically extracted and any outlier features are removed by the Boost-Layer. A spinal structured multi-output layer is then applied to the output to capture the correlation between spinal landmarks.*

![image4](.\assets\img\posts\20210714\ispine4.png)
*Conceptualized diagram of our BoostLayer module. (a) The presence of outliers in the feature space impedes robust feature embedding. (b) The BoostLayer module detects outlier features based on a statistical properties. We use an orange dashed line to represent the outlier correction stage of the BoostLayer. For the sake of brevity, we did not include the biases and activation function in the diagram. (c) After correcting outliers, the intra-class feature variance is reduced, allowing for a more robust feature embedding.*

![image5](.\assets\img\posts\20210714\ispine5.png)
*Empirical results of our BoostNet algorithm. (a) The landmarks detected by our BoostNet conforms to the spinal shape more closely compared to the ConvNet detections. (b) The BoostNet converges to a much lower error rate compared to the ConvNet.*

### Dataset
S2VR was validated on a dataset composed of 439 samples from various subjects. Seventeen vertebrae from the thoracic and lumbar spine were selected for spinal shape characterization. Each vertebra is located by four landmarks with respect to four corners thus resulting in 68 points per spinal image. The leave-one-out cross-validation scheme was employed to evaluate the model's performance.

BoostNet validation was conducted on a dataset consisting of 481 spinal anterior-posterior x-ray images. All images used for training and testing showed signs of scoliosis to varying extents. Seventeen vertebrae from the thoracic and lumbar spine were selected for spinal shape characterization. Each vertebra is located by four landmarks with respect to four corners thus resulting in 68 points per spinal image. The mean squared error and pearson correlation coefficients were employed to evaluate the accuracy of the model's estimations.

## Progressive U-Net
*Abdullah et al.* proposed an approach that was a carefully-adjusted U-Net model with progressive side outputs, which was an end-to-end segmentation model that provides a fully automatic and reliable segmentation of the vertebrae associated with scoliosis measurement. 

Their experimental resulted from a set of anterior-posterior spine X-Ray images indicate that their model, which achieveed an average Dicescore of 0.993, promiseed to be an effective tool in the identification and labeling of spinal vertebrae, eventually helping doctors in the reliable estimation of scoliosis. Moreover, estimation of Cobb angles from the segmented vertebrae further demonstrates the effectiveness of our model.
![image1](.\assets\img\posts\20210714\1.jpg)
*Overview of our framework for calculating the Cobb angle in a spine X-Ray through segmentation, labeling, and identification of the relevant vertebrae.After determining the most tilted vertebrae above and below the apex, tangents are drawn by extending the upper edge of the upper vertebra and lower edge of the lower vertebra. From these tangents, the Cobb angles are calculated and the scoliosis can be classified.*
### Approach
① Vertebrae Segmentation and Labeling
They proposed an algorithm 1 that training for vertebrae segmentation from spine X-Ray images. Here they proposed a progressive U-Net with some careful adjustments.Their model had an encoder and a decoder with skip connections. In each encoder layer, two 3 × 3 convolutions are followed by instance normalization, ReLU activation, and a 2×2 max-pooling. A dropout is applied in every encoder and decoder stage of the network. They generated side-outputs in every stage of the decoder.
![image11](.\assets\img\posts\20210714\2.jpg)
* Architecture of our segmentation network (Progressive U-Net): Side outputs at three different stages of the decoder are generated and progressively added to the next stage side-output. The output from the third side-output is added to the last stage before the final convolution to generate the final segmentation output.*
②Measurement of Scoliosis
Their pipeline made use of the vertebrae segmentation in
estimating Cobb angles. Algorithm 2 automatically calculates the Cobb angle by analyzing the contours from the segmented mask. When well-separated from others, each of the contours represents a vertebra relevant to the measurement of scoliosis.
![image2](.\assets\img\posts\20210714\3.jpg)
![image3](.\assets\img\posts\20210714\4.jpg)
*From input X-ray image (left), to segmentation mask prediction (middle), to vertebrae identification and scoliosis measurement (right) in our pipeline.*
![image5](.\assets\img\posts\20210714\5.jpg)

## U-Net + resNet
U-net key point detection + resNet classification
One of the problems faced is that one can locate the approximate target location, but the spine has many similar structures, which leads to the phenomenon of skipping at the beginning of the prediction. Therefore, imagine an improved Loss, which mainly uses the same distance between the points. There is a constraint on the distance, so this distance is added to Loss.Author named him posiLoss. Later, he saw a similar improvement in a paper.

```javascript
class posiLoss(nn.Module):
    def __init__(self,alph=50, beta=100):
        super(posiLoss, self).__init__()
        self.alph = alph
        self.beta = beta
        self.criterion_part1 = nn.MSELoss()
        self.sz = 11
        self.topKposi = 5

    def posiLoss(self, pred_heatmap, gt_heatmap):
        n,c,h,w = pred_heatmap.shape
        n_loss = list()
        for n_idx in range(n):
            # print("n:",n)
            pred_posiRation = self.relationPosi(pred_heatmap[n_idx])
            gt_posiRation = self.relationPosi(gt_heatmap[n_idx])
            psoiLossL = torch.Tensor(torch.abs(torch.sub(pred_posiRation, gt_posiRation))).cuda()
            # print("psoiLoss", psoiLossL)
            ret_psoiLoss = torch.sum(torch.topk(psoiLossL, self.topKposi).values)
            # print("ret_psoiLoss", ret_psoiLoss)
            n_loss.append(ret_psoiLoss)
        ret_n_loss = torch.mean(torch.Tensor(n_loss))
        return ret_n_loss

    def relationPosi(self, heatmap):
        # print(heatmap.shape)
        ret = list()
        ret.append(self.criterion_part1(heatmap[0], heatmap[1]))
        for i in range(1, self.sz-1):
            # print("i:",i)
            up = self.criterion_part1(heatmap[i-1], heatmap[i])
            down = self.criterion_part1(heatmap[i+1], heatmap[i])
            # print("down",down)
            ret.append(torch.mean(torch.Tensor((up, down))))
        ret.append(self.criterion_part1(heatmap[self.sz-1], heatmap[self.sz -2]))
        return torch.Tensor(ret)

    def forward(self, pred_heatmap, gt_heatmap):
        mse_loss = self.criterion_part1(pred_heatmap,gt_heatmap)
        # print("mse_loss", mse_loss)
        posiLosss = self.posiLoss(pred_heatmap,gt_heatmap)
        # print("posiLosss",posiLosss)
        return self.alph*mse_loss+self.beta*posiLosss
```



## Reference
[1]iSpine,http://digitalimaginggroup.ca/ispine/scoliosis.html

[2]Haoliang Sun, Xiantong Zhen, Chris Bailey, Parham Rasoulinejad, Yilong Yin, and Shuo Li. Direct Estimation of Spinal Cobb Angles by Structured Multi-Output Regression. The 25th international conference on Information Processing in Medical Imaging (IPMI), Boone, USA, 2017.

[3]Hongbo Wu, Chris Bailey, Parham Rasoulinejad, and Shuo Li. Automatic Landmark Estimation for Adolescent Idiopathic Scoliosis Assessment using BoostNet. 20th International Conference on Medical Image Computing and Computer Assisted Intervention (MICCAI), Quebec City, Canada. 2017.

[4]Abdullah-Al-Zubaer Imran,Chao Huang,Hui Tang, Wei Fan, Kenneth M.C. Cheung, Michael To,Zhen Qian, and Demetri Terzopoulos.Analysis of Scoliosis From Spinal X-Ray Images

[5]CSDN author dlvector
https://blog.csdn.net/github_38148039/article/details/109562997