# Image-Super-Resolution
Computer Vision Project - 6th Semester


Image super-resolution through deep learning. This project uses deep learning to upscale 16x16 images by a 4x factor. The resulting 64x64 images display sharp features that are plausible based on the dataset that was used to train the neural net.


# How it Works
In essence the architecture is a DCGAN where the input to the generator network is the 16x16 image rather than a multinomial gaussian distribution.
In addition to that the loss function of the generator has a term that measures the L1 difference between the 16x16 input and downscaled version of the image produced by the generator.
The adversarial term of the loss function ensures the generator produces plausible faces, while the L1 term ensures that those faces resemble the low-res input data. We have found that this L1 term greatly accelerates the convergence of the network during the first batches and also appears to prevent the generator from getting stuck in a poor local solution.
Finally, the generator network relies on ResNet modules as we've found them to train substantially faster than more old-fashioned architectures. The adversarial network is much simpler as the use of ResNet modules did not provide an advantage during our experimentation.

# Requirements
You will need Python 3 with Tensorflow, numpy, scipy and moviepy

