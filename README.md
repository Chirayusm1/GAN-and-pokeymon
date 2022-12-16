# GAN-and-pokeymon
The Goal
As the title points out, the goal of this post is to walk through the process of creating fake Pokemon using 
a Generative Adversarial Network (GAN). Hopefully by the end of this post, there will be some serviceable Pokemon created by this system!

GAN is a form of unsupervised learning, where two neural networks face off in conflict with each other. For the task of image generation, 
the first neural network tries to generate fake images using a seed of random numbers, or even starter images. This neural network is known as the generator. 
The opponent: a neural network that learns to differentiate between real and fake images. This agent is called the discriminator.

GANs are used to generate data — it’s in the name. GANs can be used to make realistic images, such as human faces that aren’t actually real, 
and they can augment pre-existing images. An open and interesting research application for GANs is how they can be used to augment small datasets 
by generating more samples for another AI agent to train on. 
While GANs are often used with images, they can be used for generating text, audio or other data. 
GANs have been a topic at the forefront of ethics in machine learning, especially due to their ability to generate “deepfakes” — fake 
images, audio, or video that attack a target person by depicting actions that paint the subject in a bad light.

I will outline an approach for creating deep convolutional GANs, or DCGANs for short. 
All this means is that the neural networks I am using are convolutional neural networks, rather than standard linear networks. On to the fake Pokemon!

Data Processing
I am using a Kaggle dataset created by user kvpratama, with images of over 800 Pokemon. For GANs, ~800 images is a small dataset; 
during training of my early models I was unable to get more than indistinct outlines of what could be Pokemon due to the small training size. 
In order to solve this problem, I used PyTorch transforms to create mirrored and different colored training images. 
This tripled the size of my training data, and I came up with much better results.

Conclusions and Future Work
In this article, many different models are presented, and the best ones’ results are shown. 
The results don’t scream Pokemon to me, but the potential is there with a bit more work and fine tuning. 
GANs are difficult to get right, but I think this is a good first introduction and something to expand on in the future.

I have outlined many ways to improve my current system. Among those, I want to create bigger kernel sizes at the 64x64 image size and see if I get better results. 
I also may increase the number of filters in this image size to get more detailed images. If I can find a way to manage my Kaggle GPU memory better, 
I will increase to 128x128 or higher image sizes. 
In the future, I may also look for additional datasets to pull in from similar art styles to Pokemon so I can generate crossover characters.
