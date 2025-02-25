# Proving the learnability of 3D LUTs

In this first experiment, the goal is to prove the general learnability  and generation of 3D LUTs with a Convolutional Neural Network (CNN).

- In [01_Img2LUT_CNN_BW_LUT.ipynb](https://github.com/ns144/3D-LUT/blob/main/01_CNN_Img2LUT/01_Img2LUT_CNN_BW_LUT.ipynb) we prove that its possible to learn a 3D LUT with images edited with a black and white 3D LUT. We validate our model in [01_Val_ResNet_BW_Models.ipynb](https://github.com/ns144/3D-LUT/blob/main/01_CNN_Img2LUT/01_Val_ResNet_BW_Models.ipynb) 
- In [02_Img2LUT_CNN_Fujifilm_LUT.ipynb](https://github.com/ns144/3D-LUT/blob/main/01_CNN_Img2LUT/02_Img2LUT_CNN_Fujifilm_LUT.ipynb) we compare our approach to existing conventional 3D LUT calculation methods with Fujifilm RAW and JPG images.
- In [03_Img2LUT_CNN_AutoEdit_LUT.ipynb](https://github.com/ns144/3D-LUT/blob/main/01_CNN_Img2LUT/03_Img2LUT_CNN_AutoEdit_LUT.ipynb) we train our model to automatically edit and enhance images based on original RAW images and the same images edited with Adobe Lightroom

 