# GAN-Study

![alt text](cover.jpg)

**Generative Adversarial Network** is an unsupervised task in AI that can 'generate' credible images from scratch that resembles any given dataset.The technique has been successfully used for high-fidelity natural image synthesis, data augmentation tasks, improving image compressions, and more. This repository is a study and/or exploration of this domain and the fantastic applications of it.

## GAN in brief
Essentially, GAN has two main components- a **Generator** and a **Discriminator** model. The generator is tasked with learning features from the input image dataset and producing its own (fake) versions. Conversely, the Discriminator takes the *'Real'* and the *'Fake'* images and attempts to identify them correctly. As the GAN is trained the two models simulteanously get better at their job of fooling each other until the GAN produces synthetic images that are so accurate that its almost indistinguishable from the source image.

#### Further Reading
- [A Gentle Introduction to Generative Adversarial Networks (GANs)](https://machinelearningmastery.com/what-are-generative-adversarial-networks-gans/)
- [Inside GAN Architecture](https://medium.com/@Packt_Pub/inside-the-generative-adversarial-networks-gan-architecture-2435afbd6b3b)
- [GAN with Pytorch](https://towardsdatascience.com/getting-started-with-gans-using-pytorch-78e7c22a14a5)
