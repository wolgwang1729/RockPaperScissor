# RockPaperScissor
A deep learning project that implements a  Rock-Paper-Scissors game using object detection techniques. The model is trained to recognize hand gestures representing rock, paper, and scissors.

## Project Overview
The goal of this project is to detect the rock, paper and scissor in the image

## Model Architecture
The model architecture used is Faster R-CNN with a ResNet-50 FeaturE Pyramid Network backbone.

## Dataset
The dataset used for training the model is obtained from Roboflow. The dataset contains images of hands showing rock, paper, and scissors gestures. The dataset is split into training, validation, and test sets.

## Training
The model is trained using the Detectron2 library. The training is done for 1500 iterations with a batch size of 2. The learning rate is set to 0.0025.
Cofiguration:

## Results
The model is evaluated on the validation and test sets.The model achieves an AP50 of 52.89 on the validation set. On the test set, the model achieves an AP50 of 45.64.
