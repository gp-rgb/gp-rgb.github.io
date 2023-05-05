# animal classifier

tasked with the creation of a classifier capable of differentiating up to 10 different animals. to be adapted from fastai cat vs dog classifier.

## class selection

there exist (in my mind) two schools of thought as to how to select the 10 animals to be used in the classifier. animals of similar species will likely result in more difficulty generating classification accuracy (but a more impressive model), whereas selecting animals that look very different will result in an easier process of creating a very successful classifier. 

for the first iteration of this model, i'm electing to choose animals with strong distinguishing characteristics so that i can learn the basics of fastai before pushing the model to its limits. 

1. kangaroo
2. koala
3. bilby
4. fairy penguin
5. cassowary
6. ibis
7. goanna
8. red-bellied black snake
9. frill-necked lizard
10. platypus

the choice of only australian animals is purely sentimental. the group consists of 3 marsupials, 3 birds, 3 reptiles and 1 monotreme.

## model configuration

a resnet18 model is to be used as a backbone for this example. resnet has excellent transfer-learning performance on image classification problems.

a multiclass loss function is to be designed for the classifier. i think cross-entropy is a good selection, as it is well-suited to non-binary (multiclass) classification problems.

## training and testing

the model was trained on 30 images per class, and tested with one image per class (300 total training images and 10 total testing images). fine-tuning resnet over 3 epochs is a suitable training method, and yielded great results. the model was able to identify all testing images with over 99% certainty.
