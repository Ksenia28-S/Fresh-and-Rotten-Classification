# Fresh-and-Rotten-Classification

In this project, my goal was to develop a model that can accurately classify vegetables and fruits, as well as determine if they were fresh or rotten. Firstly, i built my own model and then tested a pre-trained ResNet-18 model.

## Project steps:

1. Data preparation. Class distribution analysis. Using downsampling to address class imbalance.
2. Image augmentation.
3. Selection of a neural network architecture for image classification. Developing a multi-head model.
4. Improving the model by adding Batch Normalization after convolutions.
5. Fine-tuning a pre-trained ResNet model.
6. Assessing the quality of models on a test data set. 

## Results
F1-scores for 3 models. 

| Class | Baseline | Modified Baseline | Resnet |
| --- | --- | --- | --- |
| apples | 0.95 | 0.97 | 0.99 |
| banana | 0.97 | 0.98 | 0.99 |
| bittergroud | 0.99 | 0.98 | 1.00 |
| capsicum | 1.00 | 1.00 | 1.00 |
| cucumber | 0.85 | 0.92 | 0.98 |
| okra | 0.81 | 0.92 | 0.98 |
| oranges | 0.95 | 0.97 | 0.99 |
| potato | 0.97 | 0.97 | 0.99 |
| tomato | 0.99 | 1.00 | 0.99 |

**Conclusions:**

* A simple CNN with sequential convolutional layers and pooling layers and two separate blocks for classifying fruit type and freshness shows a fairly good result, achieving an accuracy of 0.94 in both tasks. However, precision and recall values ​​are low for the smallest classes - cucumber and okra.

* Adding Batch Normalization after the convolutional layers improved the quality of the model to an accuracy 0.97 in the first task and 0.95 in the second. Also, precision and recall for the smallest classes became higher. Apparently, this modification reduced overfitting and improved the generalization ability of the model.

* The ResNet-based model gave the best result, which is not surprising. ResNet already has knowledge about various features that can be useful for my dataset as well. In the task of classifying fruits and vegetables, this model achieved an accuracy of 0.99. Precision, Recall and F1-score also show that the model works well. When separating fresh and spoiled fruits, the model correctly performed the classification in 98% of cases. Precision, Recall and F1-score for both classes are also 0.98. In general, the model demonstrates high efficiency.
