# 3D-LUT

In this work, we attempt to transform digital images into the look of various analogue film stocks, leveraging the power of generative artificial intelligence (AI) performing this style translation based on the input image. We focus on the aspect of color rendition with the goal of transforming images without a loss of resolution or image quality to make our work applicable in professional photography.

Instead of a pixel-based image-to-image translation, we use 3D lookup tables (LUTs) to manipulate the colors of an input image to avoid the limitation in image resolution.

To generate 3D LUTs we downscale the high-resolution input image to a resolution of 256 x 256 pixels. Based upon this low-resolution image, the model generates a 3D LUT that is then used to edit the original image. For an 8 bit LUT, our model has to learn to predict 8x8x8x3=1536 output values. In comparison, if we would instead use a pixel-based image-to-image translation with a 40.2 megapixel high-resolution RGB image, our model would have to predict 120.6 million output values. 
With our approach, we can preserve the resolution of the original image while still being able to do a great deal of color manipulation efficiently. This general and simplified idea of our architecture, visualized in the following figure, will be the foundation of all experiments carried out in our work.

![Architecture overview](/Images/Simple_Architecture.jpg)

All Jupyter Notebooks are available as PDFs in [PDF](https://github.com/ns144/3D-LUT/tree/main/PDF)

You will also find HTML files of the notebooks next to the notebook files.

## Learning 3D LUTs with paired image data

See:  [01_CNN_Img2LUT](https://github.com/ns144/3D-LUT/tree/main/01_CNN_Img2LUT)

In this first experiment, the goal is to prove the general learnability and generation of 3D LUTs with a Convolutional Neural Network (CNN). The CNN receives an RGB image as input and outputs a 3D LUT. The underlying assumption of the experiment is that the generation of a 3D LUT is comparable to the generation of images. In the second stage of the experiment, the performance of CNN-generated 3D LUT is compared to a 3D LUT based on conventional calculations to see the accuracy and speed of AI in the computationally expensive task of estimating LUTs. We will use the mean squared error (MSE) on the validation target images and the generated images to test the performance and generalization of our model. To prove that our model is truly capable of learning image-adaptive 3D LUTs we train our model to enhance images in the third step.   

Below we show some of the images edited with our model trained in the third step. The images on top are the original images and the images in the second row are the images edit by our model:

![Automated edited images](/Images/AutoEditImages.jpg)



## Learning 3D LUTs with unpaired image data

As we do not have access to paired image data for analog film images and digital images we have to find an approach that can handle the challenges of unpaired image data. We included our 3D LUT model in the following architectures:

- GAN: [02_GAN_Img2LUT](https://github.com/ns144/3D-LUT/tree/main/02_GAN_Img2LUT)

- CycleGAN: [03_CycleGAN_Img2LUT](https://github.com/ns144/3D-LUT/tree/main/03_CycleGAN_Img2LUT)

- StarGAN: [04_StarGAN_Img2LUT](https://github.com/ns144/3D-LUT/tree/main/04_StarGAN_Img2LUT)

We achieved the best results with StarGAN, which also enables us to translate between different films with a single model. 
The following images show test images translated by our StarGAN based model to the looks of Kodak Gold, Cinestill 800T and Kodak Portra: 

![Ex02](https://github.com/user-attachments/assets/74057b31-36e3-4aa8-bf08-c08b3e584884)
![Ex08](https://github.com/user-attachments/assets/a292bb00-3259-4e4e-b2a7-5284dd51df67)
![Ex09](https://github.com/user-attachments/assets/6d08fbd4-89ec-47e1-ab2f-42dbe114cae6)
![Ex14](https://github.com/user-attachments/assets/33aede52-1014-41d4-a186-fc493c8d2cd8)
![Ex11](https://github.com/user-attachments/assets/31a0e3bb-34d7-48a0-a0df-8c029a62ddb7)
![Ex13](https://github.com/user-attachments/assets/99b65da9-10b0-4ebc-9e2f-620728f64e2e)
