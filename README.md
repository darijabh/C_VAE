# Implementation of (C)VAEs with MNIST data.
"Auto-Encoding Variational Bayes" by Diederik P. Kingma and Max Welling (2013).

Variational Autoencoders (VAEs) are a powerful and versatile deep learning technique. Applied to the MNIST dataset, VAEs learn to generate new handwritten digit images. They work by encoding each 28x28 pixel image into a smaller, compressed representation called a latent space. This latent space captures the essential features of the digits, like the overall shape and style. From this compressed representation, the VAE can then decode and reconstruct the image, generating new variations of handwritten digits similar to those it was trained on. This process allows VAEs to not only reproduce existing digits but also create entirely new ones that maintain the characteristics of the MNIST dataset, effectively learning the underlying distribution of handwritten digits.

Unlike regular autoencoders, VAEs learn a probabilistic mapping. Instead of just points, they learn a distribution in the latent space. This allows them to generate new data points similar to the training data by sampling from this distribution. Think of it like understanding the general layout of a city and being able to create plausible new street layouts.

In this notebook, I impement, train & test, and evaluate a VAE and use it to synthesize new digits. I also implement a Conditional VAE (CVAE), which allows to generate digits conditionally. With CVAE, one can provide a label (e.g., "generate a 5") as an input to the model, and the model will try to generate an image of that specific digit. Unlike for VAE, both the encoder and decoder of a CVAE receive the label information. This guides the encoding and decoding processes to focus on the features relevant to the given label.

When pre-processing the data, this imlementation allows the user to:
1. Resize images (14x14 by default)
2. Binarize the images (black & white)
3. Augment the data (rotation)

