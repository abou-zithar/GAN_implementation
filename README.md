# Simple GAN for MNIST Generation

This project demonstrates the implementation of a simple Generative Adversarial Network (GAN) to generate handwritten digits using the MNIST dataset. The training is accelerated using GPU power.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Results](#results)
- [Usage](#usage)
- [Conclusion](#conclusion)

## Introduction

Generative Adversarial Networks (GANs) are a class of machine learning frameworks designed by Ian Goodfellow and his colleagues in 2014. GANs consist of two neural networks, a generator and a discriminator, which contest with each other in a game. This project focuses on using a simple GAN to generate images of handwritten digits from the MNIST dataset.

## Dataset

The MNIST dataset is a large database of handwritten digits that is commonly used for training various image processing systems. It contains 60,000 training images and 10,000 testing images. Each image is 28x28 pixels, and the dataset is available from [here](http://yann.lecun.com/exdb/mnist/).

## Model Architecture

### Generator
The generator model takes random noise as input and generates images resembling the MNIST digits. The architecture consists of:

- Dense layer with ReLU activation
- Batch normalization layers
- Reshape and upsampling layers
- Conv2DTranspose layers with ReLU activation
- Output layer with Tanh activation

### Discriminator
The discriminator model takes an image as input and outputs the probability that the image is real (from the MNIST dataset) or fake (generated by the generator). The architecture consists of:

- Conv2D layers with LeakyReLU activation
- Dropout layers for regularization
- Dense layer with sigmoid activation

## Training

Training a GAN involves training both the generator and discriminator models simultaneously. The steps include:

1. Prepare the MNIST dataset and normalize the images.
2. Define the generator and discriminator models.
3. Compile the models with appropriate loss functions and optimizers.
4. Train the models using a combination of real and generated images.
5. Use GPU acceleration to speed up the training process.

### Training Loop
The training loop includes:
- Generating a batch of random noise vectors.
- Using the generator to create a batch of fake images.
- Combining fake images with real images.
- Training the discriminator with these combined images.
- Training the generator via the discriminator's feedback.

## Results

After training, the generator produces realistic-looking handwritten digits. Below is an example of the generated output:

![Generated Output](https://files.realpython.com/media/fig_gan_mnist.5d8784a85944.gif)

## Usage

To train and generate images using the GAN, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/GAN_implementation.git
   cd GAN_implementation


  ## Ensure you have GPU support enabled with TensorFlow:
  ```sh
    pip install tensorflow-gpu
  ```
## Conclusion
This project showcases a simple implementation of GANs to generate 
handwritten digits using the MNIST dataset. The use of GPU acceleration significantly speeds up the training process. Feel free to contribute to this project by submitting issues or pull requests.
