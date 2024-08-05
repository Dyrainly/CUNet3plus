# CUNet3+: A Multiscale Connected UNet for the Segmentation of Lung Cancer Cells in Pathology Sections Stained Using Rapid On-Site Cytopathological Evaluation
The implementation of CUnet3+ and the process of performing training and validation on the ROSE dataset collected by EBUS-TNBA.

The architecture of CUnet3+ is described in the following section:

Article address:https://www.sciencedirect.com/science/article/pii/S0002944024002104

> [!IMPORTANT]
> The original paper describes the detailed architecture of CUnet3+ in the figure below:

![Figure3](https://github.com/Dyrainly/CUNet3plus/blob/main/Figure3.png)

![Figure2](https://github.com/Dyrainly/CUNet3plus/blob/main/Figure2.png)

> [!IMPORTANT]
> The accuracy results of the model seem to be impressive. On the fast stained ROSE image dataset, its performance is excellent in both IoU, and Dice metrics:

![Figure5](https://github.com/Dyrainly/CUNet3plus/blob/main/Figure5.png)

## The following is a demonstration of the effect reproduced on the huggingface open source website, you can try to use it if you are interested:

Address:https://huggingface.co/spaces/lanhongyi2000/CUNet3plus

![image](https://github.com/Dyrainly/CUNet3plus/blob/main/supplment_.gif)

## Some improvements I made to the model:

1. replaced all 3*3 convolutional layers with DoConv.
2. replaced the direct connection jump module between decoding and encoding layers in UNet network with Respath.
3. in the encoding layer stage, in order to efficiently obtain the information in the ROSE image, we used Res2Net as the main framework for extracting features.
