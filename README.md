# Deep-Learning-Enginner-Assignment
PROJECT REPORT
UNet Architecture for Image Super-Resolution

1.1) UNet Architecture for Image Super-Resolution
In this project, we faced the so-called Single Image Super-Resolution (SISR) problem, which aims to infer High-Resolution (HR) images from Low-Resolution (LR) ones. The approach used by Hu, Xiaodan et al. is to exploit the U-Net network used for segmentation tasks introduced by Ronneberger et al., ending up in a network capable of enhancing image quality. The NN is shown in the image below.

It consists in two main parts: a downsampling part, composed of a series of blocks made up of convolutional layers, batch normalization, and LeakyReLU activation functions, and an upsampling part, where sub-pixel convolutional layers are used in order up-scale from low-resolution. After each upsampling, a concatenation is performed. In conclusion, in contrast to any of the common Super-Resolution network architectures, the dimensions of the input and the output images coincide during the training phase.
 
 
 
 
 
1.2) mean Absolute Error, metrics
This is the L1 loss between the pixels in SR image and the HR image. It's the sum of the absolute difference between the two sets of corresponding pixels. As it is less affected by outliers, compared to MSE, it is more likely to give images of a higher quality from the perspective of a human viewer.

PSNR (Peak signal-to-noise ratio): An engineering term for the ratio between the maximum possible power of a signal and the power of corrupting noise that affects the fidelity of its representation (usually expressed in logarithmic scale).
SSIM (Structural Similarity): A perception-based model (not estimates absolute errors) that considers image degradation as a perceived change in structural information.
 
1.3 Comparision of Trained Model Based on the metric

 


 
While Training the SSIM, PSNR, MAE Error Reduced by

 

 
Here We have seen that we got the SSIM score 0.48 and accuracy to 80% and PSNR to 19 and loss (MAE) to 0.16. After training the model
 
 



Challenges:
As the dataset contains images , and We have mentioned to reduce the pixel in range [-1,1] I have to research as I have always done the pixel normalization in range [0,1]
 After the pixel in range [-1,1], in Neural Architecture , I have to use LeakyRelu instead of Relu
I have tested on various architecture so there is issue with the gpu.
For various architecture there is various loss function in the research paper I have to understand the meaning and used the best one.

Next :
I will try SR-GAN  Architecture as they produced the best result and try to increase ssim and PSNR.


Conclusions
Implementing Unet architecture we see very good improvement in the resolution of the initial blurred images training on an actually very small dataset. With this structure, we are able to recover missing details of the input images returning images of the same size. Nevertheless, we can see some pixel rearrangement on the final result because of these subpixel layers.

