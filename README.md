# Data-Augmentation-Using-GAN-
Summer Internship 2024 Project

Human Face Generation using GANs on CelebA-HQ Dataset

This project focuses on generating realistic human facial images using Generative Adversarial Networks (GANs), a popular deep learning technique in the field of generative modeling. The primary goal is to synthetically generate high-quality facial images that resemble real human faces, leveraging the CelebA-HQ dataset, which is known for its high-resolution and diverse collection of celebrity portraits.

The project begins by downloading and preparing the CelebA-HQ dataset resized to 256x256 dimensions. For computational efficiency and faster training, a subset of 5,000 images is used. These images are preprocessed by resizing them to 64x64 resolution and normalizing the pixel values to the range [-1, 1], which is standard practice for training GANs.

The architecture used for this task is a Deep Convolutional GAN (DCGAN), which consists of two main components: the Generator and the Discriminator. The Generator takes in random noise vectors and transforms them into synthetic images through a series of transposed convolutional layers. These layers gradually upsample the input and apply batch normalization and activation functions to produce images with increasing spatial dimensions and feature complexity. On the other hand, the Discriminator is a binary classifier designed to distinguish between real images from the dataset and fake images produced by the Generator. It consists of convolutional layers followed by leaky ReLU activations and dropout to prevent overfitting.

The two networks are trained in an adversarial manner — the Generator aims to fool the Discriminator by producing realistic images, while the Discriminator works to correctly classify real and fake inputs. The Binary Cross-Entropy loss function is used for both models, and the Adam optimizer is applied to update the parameters efficiently.

Training proceeds for 50 epochs, with the model generating and saving sample outputs at the end of each epoch for visual inspection. To evaluate the performance of the trained model objectively, the Fréchet Inception Distance (FID) score is calculated, which measures the similarity between the distribution of generated images and real images in a feature space extracted using a pre-trained InceptionV3 model. A lower FID score indicates better quality and diversity of the generated images. The model achieved a FID score of 32.37, which reflects decent quality given the limited dataset and training duration.

This project demonstrates the potential of GANs in the domain of human image synthesis and sets the stage for more advanced techniques such as conditional GANs (cGANs), StyleGANs, and progressive growing GANs. Applications of such technology include data augmentation for training facial recognition systems, creative arts, video game design, and even aiding in forensic investigations.

Through this implementation, valuable insights were gained into the training dynamics of GANs, common stability challenges, and evaluation methods. The project opens avenues for further experimentation, such as improving image resolution, adding labels for attribute control, and refining the network for more photorealistic outputs.


