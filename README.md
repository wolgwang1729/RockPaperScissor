# RockPaperScissor
A deep learning project that implements a  Rock-Paper-Scissors game using object detection techniques. The model is trained to recognize hand gestures representing rock, paper, and scissors.

## Project Overview
The goal of this project is to detect the rock, paper and scissors in the image

## Model Architecture
The model architecture used is Faster R-CNN with a ResNet-50 Feature Pyramid Network backbone.

## Dataset
The dataset used for training the model is obtained from [Roboflow](https://universe.roboflow.com/roboflow-58fyf/rock-paper-scissors-sxsw/dataset/14). The dataset contains images of hands showing rock, paper, and scissors gestures. The dataset is split into training, validation, and test sets.

## Training
The model is trained using the Detectron2 library. The training is done for 1500 iterations with a batch size of 2.<br/>
Configuration used for Training :
```python
cfg.merge_from_file(model_zoo.get_config_file("COCO-Detection/faster_rcnn_R_50_FPN_3x.yaml"))
cfg.MODEL.WEIGHTS = model_zoo.get_checkpoint_url("COCO-Detection/faster_rcnn_R_50_FPN_3x.yaml")
cfg.DATALOADER.NUM_WORKERS = 2
cfg.SOLVER.IMS_PER_BATCH = 2
cfg.SOLVER.BASE_LR = 0.0025
cfg.SOLVER.MAX_ITER = 1500
cfg.SOLVER.STEPS = []
cfg.MODEL.ROI_HEADS.BATCH_SIZE_PER_IMAGE = 128
cfg.MODEL.ROI_HEADS.NUM_CLASSES = 3
```

## Results
The model is evaluated on the validation and test sets. The model achieves an AP50 of 52.89 on the validation set. On the test set, the model achieves an AP50 of 45.64.
