# CIFAR-10-Deep-Learning-Classifier
The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class.
There are 50000 training images and 10000 test images.

The dataset is divided into five training batches and one test batch, each with 10000 images.
The test batch contains exactly 1000 randomly-selected images from each class.
The training batches contain the remaining images in random order, but some training batches
may contain more images from one class than another. Between them, the training batches contain
exactly 5000 images from each class.

To tackle this classification problem 
# 1 - Data preprocessing:
A- Load the data , show a sample of the images in the dataset. 
B- Perform normalization for the training data and test data by dividing values in each image by 255 as it's easier 
   for the model that way to have values in range [0,1] than values in range [0,255]
C- Perform one-hot enconding to labels because most machine learning algorithms 
   require numerical input and output variables
   After encoding : 
   each label will be an array of size 10 as they are 10 classes
    let say car will be encoded as [0,0,1,0,0,0,0,0,0,0] 
# 2 - Constructing the model
   Deep learning models are constructed in this way: 
      Convolutional Layer ---> Pooling Layer ----> Flatten Layer ---> Output Layer
      in order to achieve high accuracy you can increase the number of blocks ( Conv + Pool )
      as well as BatchNomalization Layer but beware of Overfitting your model 
      = To reduce overfitting you can add Dropout Layer 
# 3 - Fitting the model to the data
    The imageGenerator class from keras.imagepreprocessing allows you to apply Data Augmentation (Horizontal flip, 
    vertical flip,zoom and so on )
    =In this model I tried 10 epochs and got 76.650% test accuracy and that's not bad for that number of epochs
    maybe for 100 epochs this model can achieve 85+ test accuracy 
# 4 - Evaluating the model
    Test the model accuracy when it predicts the output of the testdata and obtain the accuracy percentage and 
    the loss that we try to minimize
