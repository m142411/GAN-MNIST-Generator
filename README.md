# GAN-MNIST Generator

### Overview
This project demonstrates a **Generative Adversarial Network (GAN)** that learns to generate handwritten digit images similar to the **MNIST dataset**.

- **Generator:** Creates fake images from random noise.  
- **Discriminator:** Classifies images as **real or fake**.  
- The network is trained so that the Generator improves over time and produces realistic images.

All code is implemented using **TensorFlow 2.x** and **Keras**.

### Model Architecture

#### Generator
- Sequential model.  
- Starts with a **Dense layer** with 12,000 units, followed by **BatchNorm** and **LeakyReLU**.  
- Uses **Conv2DTranspose** layers to upsample images.  
- Output layer uses **tanh** to scale pixels to `[-1, 1]`.

#### Discriminator
- Sequential model.  
- Uses **Conv2D** layers (64, 128 filters) with **LeakyReLU** and **Dropout(0.3)**.  
- Ends with **Flatten** and **Dense(1)** for classification.  
- Determines whether input images are real or fake.

### Loss Functions
- **Binary Cross-Entropy** is used for both Generator and Discriminator.  
- **Generator loss:** Measures how well the Generator fools the Discriminator.  
- **Discriminator loss:** Measures accuracy in classifying real and fake images.

### Optimizers
- Both models use **Adam optimizer** with a learning rate of `1e-4`.

### Training
- Train for a number of epochs.  
- For each batch:  
  1. Generate fake images from noise.  
  2. Compute Discriminator outputs for real and fake images.  
  3. Calculate losses and gradients.  
  4. Update weights.  
- Generate and save sample images after each epoch to monitor progress.

### Generating Images
- Use a **fixed noise vector** to generate images consistently.  
- Images are displayed in a **4x4 grid**.  
- Pixel values are scaled back to `[0, 255]`.  
- Saved as PNG files after each epoch.


## Project Summary 

This project implements a **Generative Adversarial Network (GAN)** that can generate realistic handwritten digit images similar to the **MNIST dataset**.  
The GAN consists of two neural networks: the **Generator**, which creates fake images from random noise, and the **Discriminator**, which classifies images as real or fake.  
The networks are trained together so that the Generator improves over time and produces highly realistic images.  

---
