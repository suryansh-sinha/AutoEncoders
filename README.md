# VanillaAutoencoder
PyTorch implementation of an Undercomplete AutoEncoder that learns the latent space representation of images from MNIST dataset. I've used both ANN and CNN architectures in the Encoder, Decoder in different implementations.

# Autoencoder Using ANN.
We're using an artificial neural network in the encoder and decoder architectures.

## Encoder 
The encoder has 1 input layer and 1 hidden layer having 256 nodes with ReLU as activation.

## Latent Space Representation
The latent space representation or code has 7 hidden nodes. So, we're compressing the 28*28 image into a 1D vector of size 7.

## Decoder
The decoder has 1 hidden layer having 256 nodes followed by ReLU activation. The output layer has 28*28 nodes followed by Sigmoid as activation.