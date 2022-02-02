# Human_activity_recognition

This is an application built to show how human action classification can be done using 2D Pose Estimation and LSTM RNN machine learning models. 

2D pose estimation is done using Facebook AI Research's Detectron2. 
A LSTM model is used to classify actions from 2D pose estimation output from a sequence of consecutive frames on a video. 


## LSTM training

have trained our own LSTM model from data set given under https://github.com/stuarteiffert/RNN-for-Human-Activity-Recognition-using-2D-Pose-Input

Since we are using Detectron2 for pose estimation, we have retrofitted the dataset to map to Detectron2 output format for training our LSTM model. (Original dataset is created using [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) library which output 18 keypoints (or more) per human from the input image while Detectron2 produces only 17 keypoints)

Model classifies the action into 6 categories
- JUMPING
- JUMPING_JACKS
- BOXING
- WAVING_2HANDS
- WAVING_1HAND
- CLAPPING_HANDS

Speciality about this app is that we are using pytorch libraries for both Pose Detection and LSTM. Detectron2 is written using pytorch. Our LSTM model is built using pytorch and is trained using pytorch-lightining. pytorch-lightning makes the training code very easy and concise.

We have trained our LSTM model and have saved the best model at *models/saved_model.ckpt*, same is used in the application for inferencing when you run the application. 

<p><img src="" align="center" height="550">
