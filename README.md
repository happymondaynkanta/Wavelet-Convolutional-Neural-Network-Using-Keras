# Wavelet-Convolutional-Neural-Network
Wavelet convolutional neural network  combines a multiresolution analysis and convolutional neural network into a single  model to achieve computer vision task.

## Model Architecture of wavelet convolutional neural network
![wavelet-cnn](https://user-images.githubusercontent.com/63404097/153762968-c4fccfaf-9940-41ea-ae1e-29630d4eecb8.png)

### Description wavelet convolutional neural network connectivity
 Overview of wavelet CNN with 4-level decomposition of the input image. Wavelet CNN processes the input image through
convolution layers with 3 × 3 kernels and 1 × 1 padding. The number after Conv denotes the number of channels of the output. 3 × 3
convolutional kernels with the stride of 2 and 1 × 1 padding are used to reduce the size of feature maps. Additionally, the input image is
decomposed through multiresolution analysis and the decomposed images are concatenated channel-wise. The projection shortcuts are done
by 1 × 1 convolutions. The output of convolution layers is vectorized by global average pooling followed by a fully connected layer (fc).
The size of the output is equal to the number of classes included in the input dataset.
[Click here to read the paper](https://arxiv.org/pdf/1805.08620.pdf)

### Multi-Resolution Analysis of Discrete Wavelet Transform Decomposition
At each level of decomposition, there sub-bands of images generated in which the approximate coefficient whichis the low-frequency component is further decomposed in the subsequent level to generate another sub-bands of images.  

