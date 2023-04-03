Introduction:
In this article, we will discuss a binary classification problem using a deep learning model. The dataset used in this study does not have labels for the test set, so we assume all the test labels to be 1. Due to this assumption, the confusion matrix accuracy is approximately 0.5. We trained our model using Google Colab with Keras. We were able to improve the accuracy on the validation set to 0.888 by adding a Leaky ReLU activation function and an additional layer to the training model.

Model Architecture:
layer 1:
input image 64*64*1 (gray scale)
2 convolutional layers (kernal 3, 1 stride, 64 layers) with leaky Relu
1 batch_normalization layer
1 max_poooling (kernel 2*2 , stride 2)
1 droup (0.5)

output 20*20*64

Layer 2: 
1 convlutional layer (kernal 3, 1 stride, 32 layers) with leaky Relu
1 batch_normalization layer
1 max_poooling (kernel 2*2 , stride 2)
1 droup (0.5)

output: 6*6*32

after the two layers
flatten the features into 1152*1
and use dense and dropout to make it into 1 class output with posibility

Results:
When we trained the model on a small quantity of data, the accuracy on the validation set was 0.8882, and the training accuracy was 0.8652. After training the model on the entire dataset for 25 epochs, the training accuracy improved to 0.8730. However, due to the unavailability of the actual labels for the test set, we had to assume all labels to be 1, resulting in a test accuracy of 0.48224. Due to this assumption, we cannot draw an AUC curve for our model.

Conclusion:
In conclusion, we developed a deep learning model with a two-layer architecture that achieved a high accuracy rate on the validation set. However, due to the absence of actual labels for the test set, we had to assume all labels to be 1, which negatively impacted the test accuracy. Further studies with labeled test data are needed to evaluate the model's true performance.
