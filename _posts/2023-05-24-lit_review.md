# Literature Review
Here we explore several models used in literature on similar problems.

## The Basic Convolutional Neural Network

The basic neural network struggles to identify patterns in images, as it has no support for understanding data in grids. The first convolutional neural network was proposed in 1990, as a way to adapt the basic neural network to recognise visual patterns in images \cite{liang:20} . It is made up of a series of different layers, the three types including the convolutional, pooling and fully-connected layers \cite{liang:20}.

The convolutional and pooling layers are often stacked together, as they analyse patterns in the image and extract these patterns into features \cite{yamashita:18}. Convolutional layers perform convolutions on the image with gradually more complex "kernels" -- kernels being small matrices representing the pattern of interest at any given layer \cite{yamashita:18}. Pooling layers down-sample the image in order to find patterns at all scales of the image \cite{liang:20}.

The fully-connected layer, on the other hand, is usually only placed at the end of the network in order to condense the features into actual class predictions, in the case of a classification model \cite{yamashita:18}.

![cnn](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/69208d41-de8d-4310-b509-352b2a4b19f9)

## Other Convolutional Architectures
A lot of problems use a pretrained CNN, rather than building one from scratch. This allows the models to perform deep feature detection while saving a significant amount of training time \cite{kim:22}. These models are often trained on very large "natural image" datasets, like ImageNet \cite{kim:22}. The pre-training process leads to a very advanced model that is only able to perform generic tasks -- but these "backbone" models can be transferred to very complex tasks with a small amount of specialised training \cite{iman:23}. 

![backbones](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/ddab02be-8ba3-48d6-a582-d227bdfbef98)

### VGG
Designed for image-wide classification problems, VGG is one of the older transfer learning models \cite{yang:21}. It consists of multiple convolutional layers, and has 3x3 kernel sizes \cite{yang:21}.

### ResNet
ResNet implements connections between layers detecting high-level features and those detecting low-level ones \cite{yang:21}. This allows ResNet models to get very deep with minimal training time, as these connections help optimise the training process \cite{yang:21}.

### DenseNet
DenseNet is a modification of the ResNet model, with additional "dense" layers between convolutional layers \cite{yang:21}. These dense layers preserve high-level features as the model progressively downsamples the original image, which allow good performance with fewer trainable parameters \cite{yang:21}.
