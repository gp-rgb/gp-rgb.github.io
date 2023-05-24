# animal classifier metrics

now it's time to look at the performance of the mdoel in-depth. i'd like to generate some metrics for the model.

## error rate vs. epoch
![download (1)](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/6b47ab16-39e2-41d1-9334-cb135c1749ef)

the training process can be most effectively visualised with a loss-iterations graph. the losses for both the training and validation set are shown. most often, we are only interested in the performance on the validation set, as it gives an indication of how well the model performs on new data.

## biggest Ls
![download (2)](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/48075702-0dbb-427b-909d-e4eec5ae07c5)

9 of the greatest loss datapoints are shown. these show the data points that the model was least certain about, or ones that the model misclassified. Apart from the misclassification of a goanna as a koala, most other misclassifications were all between animals of the same class (marsupials, reptiles, birds, etc.).

## confusion matrix
![download](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/04ddf3ac-a0e8-4878-bd40-bece9db243e7)

Shows a different visualisation of common misclassifications. 

## t-SNE visualisation
![download (3)](https://github.com/gp-rgb/gp-rgb.github.io/assets/131956221/8b794744-f827-4e14-be3e-5c98918569e5)

the t-sne visualisation shows a compressed version of the model. the many-dimensional cnn is generalised into two axes, and various datapoints are plotted into different prediction clusters. the colours of the datapoints indicate their true class. the code used to generate this graph is shown below.


A good explanation of t-sne is available [here]. (https://distill.pub/2016/misread-tsne/ "Title")

    from sklearn.manifold import TSNE

    def visualise_with_tsne(learn, p=5,l=100):
      pred,actual = learn.get_preds()
      pred_np = pred.numpy()
      actual_np = actual.numpy()
      tsne = TSNE(n_components=2,perplexity=p,learning_rate=l)
      tsne_data = tsne.fit_transform(pred_np)

      sct = plt.scatter(tsne_data[:, 0], tsne_data[:, 1],c=actual_np)
      plt.xlabel('t-SNE Dimension 1')
      plt.ylabel('t-SNE Dimension 2')
      plt.title('t-SNE Visualization')

      plt.legend()
      legend_elements = sct.legend_elements()
      legend = plt.legend(handles=legend_elements[0], labels=legend_elements[1])
      plt.show()


