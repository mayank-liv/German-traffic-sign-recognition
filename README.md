# German-traffic-sign-recognition
### Deep Learning project to identify traffic signs. Part of a larger project to aid self-driving cars


## Overview - 

In this project, I aim to build a model to classify traffic signs into various categories, using Python and Keras.

This project is a minor project, which forms a part of a larger project to aid self-driving cars. One of the most important things needed in a self-driving car is a mechanism to identify any traffic sign that the car's camera might capture, and to use it to perform future operations in the car, like stopping infront of a stop sign, or to not park in a no-parking zone.

This project aims to develop a model to exactly that.


## Dataset -

The dataset for this project was available at https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign. The training data contains 39,209 labelled data while the test data has 12,630 unlabelled data.

The dataset contains traffic sign images belonging to 43 different classes, and there were enough images belonging to each class to be able to train the model well. The initial implementation of the project doesn't use data augmentation as there is already enough images present to train the model to a satisfactory performance level.



## Model Used -

I used a Deep Neural Network model, with 8 layers in total, as shown in the table below.

| Layer | Output Shape | No. of parameters|
|-------|--------------|------------------|
| Conv2D) | (None, 48, 48, 8) | 224 |
| Batch Normalisation | (None, 48, 48, 8) | 32 |
| MaxPooling2 | (None, 47, 47, 8) | 0 | 
| Conv2D | (None, 45, 45, 16) | 1168 |  
|  Batch Normalisation | (None, 45, 45, 16) | 64 |
| MaxPooling2 | (None, 44, 44, 16) | 0 |
| Flatten | (None, 30976) | 0 | 
| Dense | (None, 43) | 1332011 |

Total parameters = 1,333,499
Trainable parameters = 1,333,451
Non-trainable parameters = 48

The layers we used in the Deep Neural Network also had dropout in it, which hasn't been shown in the table, inorder to prevent overfitting.


## Training Results - 

After running the model for 50 epochs, with a batch size of 512 and a validation set containing 20% of the training data, with Adam optimizer as an evaluation metric, we ended up getting a training set accuracy of 98.78% and a validation set accuracy of 95.93%.

### Training accuracy = 98.78 %
### Validation accuracy = 95.93 %


## Test Results -

On running the data on the Test set, we end up with an accuracy of 85.39 %, which isnt't too bad.
### Test accuracy = 85.39 %


## Future improvements - 

Although the test set accuracy of 85.39% is satisfactory, it is still not good enough to be a part of an actual self-driving ca. So, since we have a lot more trainable parameters (1,333,451) than the training data (39,209 images), we must use data augmentation to develop plenty of other images to form a part of the training data. This will ensure that the model has enough training data to get the parameters trained even better than before. Also, we can develop a deeper neural network, so that the accuracy of the model can further improve. My ultimate aim is to improve the test accuracy to reach at least a threshold level of 90%, before it can be used in a prototype of a self-driving car.

