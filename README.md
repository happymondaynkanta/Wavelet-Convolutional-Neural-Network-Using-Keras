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
For 2-dimensional image input, Multi-Resolution Analysis of Discrete Wavelet Transform Decomposition is applied as a technique to decomposed the image into approximate and detail coefficient of varying frequencies and scales through low- and high-pass filters with the scale factor of 2. The approximat coefficient is the low frequency component while the detail coefficient is the high frequency component.

Approximate image
![A](https://user-images.githubusercontent.com/63404097/153786311-03fbb2f6-9941-45c9-98e6-bb0320dfaf78.PNG)


Horizontal image
![H](https://user-images.githubusercontent.com/63404097/153786330-85594e96-a0c9-4992-8892-93e6ef72ccbd.PNG)


Vertical image
![V](https://user-images.githubusercontent.com/63404097/153786343-7987f1c1-6b6f-4909-b31b-aaab34887135.PNG)


Diagonal image
![D](https://user-images.githubusercontent.com/63404097/153786351-603aad20-8778-4375-8f4e-d4380e5c5c13.PNG)



At each level of decomposition, sub-bands (LL, HL, LH, HH) of images are generated which are fed as input to the neural network. For subsequent decomposition levels, the approximate coefficient which is the low-frequency component is further decomposed to generate another sub-bands of images.

![LEVELS](https://user-images.githubusercontent.com/63404097/153786542-5a057d4a-ac90-433a-8f25-3b089ed6881a.PNG)



