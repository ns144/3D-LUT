# 3D-LUT

In this work, we attempt to transform digital images into the look of various analogue film stocks, leveraging the power of generative artificial intelligence (AI) performing this style translation based on the input image. We focus on the aspect of color rendition with the goal of transforming images without a loss of resolution or image quality to make our work applicable in professional photography.

Instead of a pixel-based image-to-image translation, we use 3D lookup tables (LUTs) to manipulate the colors of an input image to avoid the limitation in image resolution.

To generate 3D LUTs we downscale the high-resolution input image to a resolution of 256 x 256 pixels. Based upon this low-resolution image, the model generates a 3D LUT that is then used to edit the original image. For an 8 bit LUT, our model has to learn to predict 8x8x8x3=1536 output values. In comparison, if we would instead use a pixel-based image-to-image translation with a 40.2 megapixel high-resolution RGB image, our model would have to predict 120.6 million output values. 
With our approach, we can preserve the resolution of the original image while still being able to do a great deal of color manipulation efficiently. This general and simplified idea of our architecture, visualized in the following figure, will be the foundation of all experiments carried out in our work.

![Architecture overview](/Images/Simple_Architecture.jpg)

## Learning 3D LUTs with paired image data

![Automated edited images](/Images/AutoEditImages.jpg)



## Learning 3D LUTs with unpaired image data

