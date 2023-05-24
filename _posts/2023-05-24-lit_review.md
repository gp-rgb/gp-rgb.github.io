# Literature Review
Here we explore several models used in literature on similar problems.

## The Basic Convolutional Neural Network

The basic neural network struggles to identify patterns in images, as it has no support for understanding data in grids. The first convolutional neural network was proposed in 1990, as a way to adapt the basic neural network to recognise visual patterns in images [4] . It is made up of a series of different layers, the three types including the convolutional, pooling and fully-connected layers [4].

The convolutional and pooling layers are often stacked together, as they analyse patterns in the image and extract these patterns into features [5]. Convolutional layers perform convolutions on the image with gradually more complex "kernels" -- kernels being small matrices representing the pattern of interest at any given layer [5]. Pooling layers down-sample the image in order to find patterns at all scales of the image [4].

The fully-connected layer, on the other hand, is usually only placed at the end of the network in order to condense the features into actual class predictions, in the case of a classification model [5][1].

![cnn](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/69208d41-de8d-4310-b509-352b2a4b19f9)

## Other Convolutional Architectures
A lot of problems use a pretrained CNN, rather than building one from scratch. This allows the models to perform deep feature detection while saving a significant amount of training time [3]. These models are often trained on very large "natural image" datasets, like ImageNet [3]. The pre-training process leads to a very advanced model that is only able to perform generic tasks -- but these "backbone" models can be transferred to very complex tasks with a small amount of specialised training [2]. 

![backbones](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/ddab02be-8ba3-48d6-a582-d227bdfbef98)

### VGG
Designed for image-wide classification problems, VGG is one of the older transfer learning models [6]. It consists of multiple convolutional layers, and has 3x3 kernel sizes [6].

### ResNet
ResNet implements connections between layers detecting high-level features and those detecting low-level ones [6]. This allows ResNet models to get very deep with minimal training time, as these connections help optimise the training process [6].

### DenseNet
DenseNet is a modification of the ResNet model, with additional "dense" layers between convolutional layers [6]. These dense layers preserve high-level features as the model progressively downsamples the original image, which allow good performance with fewer trainable parameters [6].

# References
[1] Konstantinos Demertzis, Stavros Demertzis, and Lazaros Iliadis. A selective survey review of computational intelligence applications in the primary subdomains of civil engineering specializations. Applied Sciences, 13(6), 2023.
[2] Mohammadreza Iman, Hamid Reza Arabnia, and Khaled Rasheed. A review of deep transfer learning and recent advancements. Technologies, 11(2), 2023.
[3] Hee E. Kim, Alejandro Cosa-Linan, Nandhini Santhanam, Mahboubeh Jannesari, Mate E. Maros, and Thomas Ganslandt. Transfer learning for medical image classification: A literature review. BMC Medical Imaging, 22(1), 2022.
[4] Jiazhi Liang. Image classification based on resnet. Journal of Physics: Conference Series, 1634(1):012110, 2020.
[5] Rikiya Yamashita, Mizuho Nishio, Richard Kinh Do, and Kaori Togashi. Convolutional neural networks: An overview and application in radiology. Insights into Imaging, 9(4):611–629, 2018.
[6] Yuan Yang, Lin Zhang, Mingyu Du, Jingyu Bo, Haolei Liu, Lei Ren, Xiaohe Li, and M. Jamal Deen. A comparative analysis of eleven neural networks architectures for small datasets of lung images of covid-19 patients toward improved clinical decisions. Computers in Biology and Medicine, 139:104887, 2021.
