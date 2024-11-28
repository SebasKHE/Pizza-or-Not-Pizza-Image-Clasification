# Pizza-or-Not-Pizza-Image-Clasification
This is a deep learning model in which a set of food data is used to train a model so that it can predict whether the image provided is a pizza or not. Using transfer learning by leveraging Resnet's pre-trained model.

Steps to develop the model.

Download the images from the dataset, store them in a directory, assign the paths for both training and test data.

Create a custom dataset class where the image files are read and the class created for the transformation is applied to them, where they are resized to be compatible with the resnet50 model, normalised and converted to tensors.

The dataloader is created with which the datasets will be processed for both training and testing, for training the data is shuffled, except for testing.

A class is created for a custom model nn.Module where the resnet 50 network is created, and a modification is made to the last layer for binary classification in this case. We also leave the parameter pretrained = True to indicate that we will use the weights of the pre-trained model for transfer learning.

Binary Cross Entrophy Loss is defined as a loss criterion and Adam is defined as an optimiser with an LR of 0.001 and techniques such as L2 (weigh decay).

Functions are created to help plot the loss and accuracy at the end of training.

Functions are created to train and validate the model, these include a loop for each epoch and another loop to process each image from the dataset loaded into the data loader. The losses and precision are stored in lists for later visualisation of the curve in matplotlib graphs.

The model is trained, at the end it displays the accuracy and loss curve, and then evaluated by displaying the accuracy on the test data.

Afterwards, two functions are created to help us plot the predictions made. The input image, the predicted class and the actual class are displayed.

The classification report and the confusion matrix are printed.

The model shows an accuracy of 90%.

Translated with DeepL.com (free version)
