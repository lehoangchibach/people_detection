# Deep Learning-Based People Counting in Images

Collaborators: Bach Le, Tsugunobu Miyake, Junnan Shimizu

## Project description
This repository implements a deep learning approach for accurately estimating the number of people present in an image, using the TJU-DHD ped_traffic dataset containing images taken from inside a car. This project will utilize the pre-trained CNN model, VGG16, to detect the people on the streets. After developing the base model, we plan to utilize the ped_campus dataset containing pedestrians on campus. In particular, we will analyze the accuracy of the model trained on ped_traffic data for ped_campus data and vice versa. Then, we will integrate both datasets and improve the model's accuracy. 

## Note

##### Milestone 1
Our Milestone 1 work is in `process_data.ipynb`. \
The training and validation images used in our project will be stored in `images/train/`, and the testing images will be stored in `images/val/`. We only use training and validation data, as TJU-DHD does not provide annotation for the test dataset.


We did not upload images to this repository as the file size is too large. Please download it from the following website.

Dataset: [https://github.com/tjubiit/TJU-DHD](https://github.com/tjubiit/TJU-DHD)

Date loader: [https://github.com/cocodataset/cocoapi](https://github.com/cocodataset/cocoapi)

##### Milestone 2
For Milestone 2, we implemented the YOLOv8 object detection model. 

In order to do so, 
