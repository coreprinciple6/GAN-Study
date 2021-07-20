
# CycleGAN
CycleGAN was used for a Generative Art competition in [Kaggle](https://www.kaggle.com/c/gan-getting-started). The task was to apply the painting style of Claude Monet on another set of images of scenaries.

![alt text](monet.png)
<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Introduction](#introduction)
* [CycleGAN](#cyclegan)
  -[Dataset](#dataset)
  -[Theory](#theory)
* [Results](#results)

## Introduction
"We recognize the works of artists through their unique style, such as color choices or brush strokes. The “je ne sais quoi” of artists like Claude Monet can now be imitated with algorithms thanks to generative adversarial networks (GANs). In this getting started competition, you will bring that style to your photos or recreate the style from scratch!

Computer vision has advanced tremendously in recent years and GANs are now capable of mimicking objects in a very convincing way. But creating museum-worthy masterpieces is thought of to be, well, more art than science. So can (data) science, in the form of GANs, trick classifiers into believing you’ve created a true Monet? That’s the challenge you’ll take on! "

## CycleGAN
"A GAN consists of at least two neural networks: a generator model and a discriminator model. The generator is a neural network that creates the images. For our competition, you should generate images in the style of Monet. This generator is trained using a discriminator.

The two models will work against each other, with the generator trying to trick the discriminator, and the discriminator trying to accurately classify the real vs. generated images.

Your task is to build a GAN that generates 7,000 to 10,000 Monet-style images. "

### Dataset
"The dataset contains four directories: monet_tfrec, photo_tfrec, monet_jpg, and photo_jpg. The monet_tfrec and monet_jpg directories contain the same painting images, and the photo_tfrec and photo_jpg directories contain the same photos.

We recommend using TFRecords as a Getting Started competition is a great way to become more familiar with a new data format, but JPEG images have also been provided.

The monet directories contain Monet paintings. Use these images to train your model."

### Theory

CycleGAN is a derivative of GAN with a unique twist. It is an image-to-image translation network that can take the features of one domain and translate it to another domain.
It trains two generators and two discriminators as opposed to one in a normal GAN. A rudimentary example would be taking images of scenaries in summer and making them look like winter time!
![alt text](https://raw.githubusercontent.com/yunjey/mnist-svhn-transfer/master/gif/cyclegan.png)

As visualized by the above picture, images from Domain A is fed to G<sub>AB</sub> (first generator) and the resultant images are of Domain B. Conversely, images from Domain B is fed to G<sub>BA</sub> (second generator) which outputs images from Domain A. The two discriminators are used to identify if the images are *real* or *fake*.


The loss is calculated with every epoch and the model is updated accordingly. Another unique concept associated with cycleGAN is **Cycle Consistency**. This concept suggests that the output of the first generator can be fed to the second generator whose output in turn, should theoreticslly, look the same as the initial inout of the first generator.
The CycleGAN uses an additional extension to the architecture called cycle consistency. This is the idea that an image output by the first generator could be used as input to the second generator and the output of the second generator should match the original image. The reverse is also true: that an output from the second generator can be fed as input to the first generator and the result should match the input to the second generator. To demonstrate with an example , lets take the case of our project. Images from Monet dataset is used to train Generator A which results 'fake'  images that look alot like the photos in the seccond dataset. If these 'fake' images are given as input to the second generator, it should(as discussed above) produce images of scenaries that look 'Monesque'. Now ideally , we would expect exact likeness to that of the first datatset, but machine learning is rarely ever 100% accurate. There is always 

Cycle consistency is a concept from machine translation where a phrase translated from English to French should translate from French back to English and be identical to the original phrase. The reverse process should also be true.

… we exploit the property that translation should be “cycle consistent”, in the sense that if we translate, e.g., a sentence from English to French, and then translate it back from French to English, we should arrive back at the original sentence

— Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks, 2017.

The CycleGAN encourages cycle consistency by adding an additional loss to measure the difference between the generated output of the second generator and the original image, and the reverse. This acts as a regularization of the generator models, guiding the image generation process in the new domain toward image translation.


## Results 
