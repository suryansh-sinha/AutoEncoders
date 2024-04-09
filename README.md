# Autoencoders
PyTorch implementations of an Undercomplete AutoEncoder and a Denoising Autoencoder that learns the latent space representation of images from MNIST dataset. I've used both ANN and CNN architectures in the Encoder, Decoder in different implementations of undercomplete autoencoder. 

## Undercomplete Autoencoder Using ANN.
We're using an artificial neural network in the encoder and decoder architectures.

### Encoder 
The encoder has 1 input layer and 1 hidden layer having 256 nodes with ReLU as activation.

### Latent Space Representation
The latent space representation or code has 7 hidden nodes. So, we're compressing the 28*28 image into a 1D vector of size 7.

### Decoder
The decoder has 1 hidden layer having 256 nodes followed by ReLU activation. The output layer has 28*28 nodes followed by Sigmoid as activation.

## Autoencoders Using CNN
We're using a convolutional neural network in the encoder and decoder architectures here.

### Encoder
The encoder architecture has -
- Conv2d, ReLU, MaxPool2d --> Output = `[16, 14, 14]`
- Conv2d, ReLU, MaxPool2d --> Output = `[32, 6, 6]`
- Conv2d --> Output = `[64, 1, 1]`

### Latent Space Representation
The latent space representation or code has size `[64, 1, 1]` thus representing an image by 64 values.

### Decoder
The decoder architecture has -
- ConvTranspose2d, ReLU --> Output = `[32, 7, 7]`
- ConvTranspose2d, ReLU --> Output = `[16, 14, 14]`
- ConvTranspose2d, ReLU --> Output = `[1, 28, 28]`

## Denoising Autoencoder
The denoising autoencoder has the same architecture as the CNN Autoencoder. The only difference is that we're adding noise to the images from the dataset. Then we're passing those images to the autoencoder. The loss is calculated by comparing the reconstructed images with the original images instead of the noisy images. Thus, the model learns the latent space representation for noisy images. 