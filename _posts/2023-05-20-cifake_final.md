# 98% accurate ResNet50 Model on CIFAKE

in just over 1 hour of training (gpu-assisted!), i have a model that performs with 98% accuracy on cifake dataset. very cool!!

<img width="260" alt="traintime" src="https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/50da9d78-e9b7-4129-9d08-bfea6b59c594">

## model selection

the review of hyperparameters led to the selection of resnet50 as the architecture that had the best trade-off between training time, and feature-detection capability. the default loss function of cross-entropy loss and the ADAM optimisation function were also found to be most effective on the dataset.

## performance

Here are some cool graphics about the model's performance

### Loss vs Iterations

<img width="433" alt="final" src="https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/8a507497-a71a-4248-a53c-db8cfa2156b8">

### confusion matrix

![download (4)](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/90ac3493-ff7b-4c5c-b4c2-79c68289e6b3)


### t-sne visualisation

![download (1)](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/926df391-113b-4560-8f05-c88e8949f371)

### top losses

![download](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/1ecae3a7-85d3-4ef5-84c2-572e8b57fe30)
