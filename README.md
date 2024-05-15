# Deep Learning-Based People Counting in Images

Collaborators: Bach Le, Tsugunobu Miyake, Junnan Shimizu

## Project description
This repository implements a deep learning approach for accurately estimating the number of pedestrians present in an image, using the TJU-DHD ped_traffic dataset containing images taken from inside a car. This project will utilize the pre-trained YOLO model trained on the COCO dataset to detect the people on the streets. Originally, we planned to utilize a pre-trained CNN model, VGG16 to detect the number of people on the streets. However, after creating the model using VGG16, we quickly realized that the loss of the model was too large. We therefore developed a YOLO (You Only Look Once) v8-based model that detects the location of pedestrians in the image. We compared the performance of the YOLO-based model and the VGG16-based model in estimating the number of pedestrians in a picture.

## Instructions
Our project dependencies is stored in `requirements.txt`.
Our Milestone 1 work is in `process_data.ipynb`. \
Our final work is in `VGG16_based.ipynb`, `yolov8_based.ipynb`, and `yolov8_measure_performance.ipynb`. We tried two different approaches for milestone 2 since the VGG16 approach was not promising. Both approaches have the data loading-preparation-training-evaluation pipeline. 

`VGG16_based.ipynb` contains the loading-preparation-training-evaluation pipeline for the VGG16-based model. `yolov8_based.ipynb` contains the loading-preparation-training pipeline for the YOLO-based model, and `yolov8_measure_performance.ipynb` contains the evaluation of the YOLO-based model. In the final report, we compared the performances of both architectures.

The training and validation images used in our project will be stored in `images/train/`, and the testing images will be stored in `images/val/`. We only use training and validation data, as TJU-DHD does not provide annotation for the test dataset. The 2 annotation JSON files will be store in `annotations`.

We did not upload images to this repository as the file size is too large. Please download it from the following website.

Dataset: [https://github.com/tjubiit/TJU-DHD](https://github.com/tjubiit/TJU-DHD)
KerasCV YOLOV8Detector Class: [https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/](https://keras.io/api/keras_cv/models/tasks/yolo_v8_detector/)
