# German-traffic-sign-recognition
### Deep Learning project to identify traffic signs. Part of a larger project to aid self-driving cars

In this project, I aim to build a model to classify traffic signs into various categories, using Python and Keras.


## Dataset -
The dataset for this project was available at https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign. The training data contains 39,209 labelled data while the test data has 12,630 unlabelled data.


## Model Used -
I used a Deep Neural Network model, with 10 layers in total, as shown in the table below.

| Layer | Output Shape | No. of parameters|
|-------|--------------|------------------|
| Conv2D) | (None, 48, 48, 8) | 224 |


