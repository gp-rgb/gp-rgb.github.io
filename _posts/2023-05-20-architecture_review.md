# ai image detection architecture review
Various architectures were tested. Most architectures tested were designed to fix what is known as the "vanishing gradient problem". this is a problem encountered when trying to deepen CNNs with more layers. Eventually, adding more layers causes feature gradients to approach zero, becoming useless.

This basic loop of code was used to generate the results that you can see. The following graphs were generated from a small subset of the CIFAKE dataset, and are used only to test each model's relative performances.

'''

backbones = [
    resnet18,
    densenet121,
    vgg16
]


for back in backbones:
    learn_lossvar=0
    learn_lossvar = vision_learner(subset_dls, back, metrics=accuracy,loss_func=CrossEntropyLossFlat(),opt_func = opt)
    learn_lossvar.fine_tune(3)
    plt.figure()

    learn_lossvar.recorder.plot_loss()
    plt.xlabel('Iterations')
    plt.ylabel('Loss')
    plt.ylim(0,1.5)
    plt.title(back)
    plt.show()
    sleep(1)


'''

## ResNet
<img width="423" alt="a_r50" src="https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/d7be1497-ad6c-4470-a5df-dcd4eb452d52">

ResNet is a very popular backbone for image classification. Where other models learn the features of the data, ResNet aims to learn residual values which eliminates vanishing gradients.

## DenseNet
<img width="428" alt="a_d161" src="https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/00feedb0-d47f-45a2-8aa0-9dc1408da4bd">


DenseNet is also a well-performing backbone in literature. It makes liberal use of fully-connected layers in a CNN, known also as Dense layers. This is an alternative solution to the vanishing gradient problem, and allows DenseNet models to have very deep feature-recognition. 

## VGG
<img width="422" alt="a_vgg19" src="https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/db2ed010-fa29-4b64-bd71-547c2a3b5b25">

VGG networks are made up of consecutively shrinking convolutional building blocks. The building blocks have convolutional filters, and pooling layers. It is used very frequently for image classification.

