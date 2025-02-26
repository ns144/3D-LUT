# Improving stability: 3D LUT generation with a CycleGAN

In comparison to the previously used GAN architecture we hope to introduce greater stability with the introduction of the CycleGAN architecture and assume that the artifacts and broken color transitions could be reduced due to the cycle-consistency and identity mapping loss. In this experiment, we aim to enable the translation between different color films with the usage of unpaired image data for the first time, and we want to reduce the amount of artifacts and increase the stability of training.

- In [Img2LUT_CycleGAN.ipynb](https://github.com/ns144/3D-LUT/blob/main/03_CycleGAN_Img2LUT/Img2LUT_CycleGAN.ipynb) we implemented and trained our CycleGAN
- In [VAL_Models.ipynb](https://github.com/ns144/3D-LUT/blob/main/03_CycleGAN_Img2LUT/VAL_Models.ipynb) we evaluate the trained models

