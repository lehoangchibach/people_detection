# Deep Learning-Based People Counting in Images

Collaborators: Bach Le, Tsugunobu Miyake, Junnan Shimizu

## Project description
This repository implements a deep learning approach for accurately estimating the number of people present in an image, using the TJU-DHD ped_traffic dataset containing images taken from inside a car. This project will utilize the pre-trained YOLO model trained on the COCO dataset to detect the people on the streets. After developing the base model, we plan to utilize the ped_campus dataset containing pedestrians on campus. In particular, we will analyze the accuracy of the model trained on ped_traffic data for ped_campus data and vice versa. Then, we will integrate both datasets and improve the model's accuracy. 

## Instructions
Our Milestone 1 work is in `process_data.ipynb`. \
Our Milestone 2 work is in `VGG16_based.ipynb` and `yolov8_based.ipynb`. As described in the next section, we tried two different approaches for milestone 2 since VGG16 approach was not promising. Both approaches have the data loading-preparation-training-evaluation pipeline, but `yolov8_based.ipynb` is more complete as we decided to use YOLO v8 architecture. We uploaded `VGG16_based.ipynb` for the reference.

The training and validation images used in our project will be stored in `images/train/`, and the testing images will be stored in `images/val/`. We only use training and validation data, as TJU-DHD does not provide annotation for the test dataset.

We did not upload images to this repository as the file size is too large. Please download it from the following website.

Dataset: [https://github.com/tjubiit/TJU-DHD](https://github.com/tjubiit/TJU-DHD)
KerasCV YOLOV8Detector Class: [https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/](https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/)

## Changes from Milestone 1
Originally, we planned to utilize a pre-trained CNN model, VGG16 to detect the number of people on the streets. However, after creating the model using VGG16, we quickly realized that the loss of the model was too large. This was due to the dataset having many images of one to five pedestrians. We modified the sampling to get more equally distributed data to train the model, which can be found on the `sample_data_equal` function in `process_data.ipynb`.

The model was still not quite useful as the loss was still greater than 3. After consulting with the professor, we decided to change the architecture to YOLO (You Only Look Once) which is used for real-time object detection. (Paper: [https://arxiv.org/pdf/1506.02640v5.pdf](https://arxiv.org/pdf/1506.02640v5.pdf)) We found a tensorflow-keras implementation of YOLO v8, which we decided to use for our project. For milestone 2, we reimplemented data preparation and finished building the loading-preparation-training-evaluation pipeline for the YOLOV8 model. We used the following tutorials and documentation to develop our pipeline.

- [https://keras.io/examples/vision/yolov8/](https://keras.io/examples/vision/yolov8/)
- [https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/](https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/)
- [https://keras.io/guides/keras_cv/object_detection_keras_cv/](https://keras.io/guides/keras_cv/object_detection_keras_cv/)

## Next steps
Currently, our training and evaluation pipeline evaluates box_loss with the Intersection over Union (IoU) metric, which evaluates how much overlap between the ground truth and prediction exists. The program also calculates average precision and average recall for the model, but the callback function that evaluates the average precision and average recall, `keras_cv.callbacks.PyCOCOCallback`, outputs -1, which is invalid. We also plan to work on the following tasks for milestone 3.

- Compare our YOLO model with the original CNN model.
- Tune hyperparameters such as learning rate and batch size.
- Train and test our model on a different dataset.

## Original Project description
This repository implements a deep learning approach for accurately estimating the number of people present in an image, using the TJU-DHD ped_traffic dataset containing images taken from inside a car. This project will utilize the pre-trained CNN model, VGG16, to detect the people on the streets. After developing the base model, we plan to utilize the ped_campus dataset containing pedestrians on campus. In particular, we will analyze the accuracy of the model trained on ped_traffic data for ped_campus data and vice versa. Then, we will integrate both datasets and improve the model's accuracy. 


