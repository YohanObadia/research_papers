# Subjects covered in FASTAI course 1. In bold what I need to dig deeper into for better understanding.
 - Affine functions and non-linearity
 - **Parameters and activations**: Recode a backward propagation from scratch.
 - Random init and transfer learning
 - SGD, Momentum and Adam
 - Convolutions
 - **Batch-norm**: how is normalization computed in fastai
 - Dropout
 - Data augmentation
 - Weight decay
 - **Res/Dense blocks**: How the double convolution and the previoux x combine
 - Image classification and Regression
 - **Embeddings**: Is embedding really just a matrix multiplication. Useful for dimensionality reduction of categorical variables to avoid them taking to much importance on the model.
 - Continuous and Categorical variables
 - **Collaborative filtering**: Read more code as to how it is implemented. Can you for example do more than one layer, and if yes how.
 - Language models / NLP classification
 - Segmentation / U-net / GAN


# Lesson 4-5:
To avoid overfitting, multiple techniques can be used:
 - Dropout
 - Weight Decay also called L2-Regularization:
 
   ![](https://latex.codecogs.com/gif.latex?L(x,y,\theta)&space;=&space;l(x,y)&space;&plus;&space;\sum\theta_i^2)

# Lesson 7:
To apply deconvolution, you can use **Nearest-Neighbors Interpolation**, **Bilinear Interpolation**, **Pixel-Shuffle**.

For training a GAN, instead of training from scratch both the **Generator** and the **Discriminator**, start by training the Generator
on another metric like MSE, then the Discriminator on those generated images, and only then, start the back and forth between the 
Generator and the Discriminator. The difficulty is the cold start problem when having both models not knowing anything and you need 
to circumvent it somehow.

To train the Generator you need to use **Spectral Normalization** to avoid both the Generator and the Discriminator to push the 
weights increasingly high. (
