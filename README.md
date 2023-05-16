# motorcycle-detection-using-yolov5-python-computer-vision
motorcycle detection  using yolov5 | python | computer vision
based on Noor Khokar's repo: https://github.com/noorkhokhar99/YOLOv8-COMPLETE-Tutorial-Object-Detection-Segmentation-Classification


### Step 1
Depending on what object detection you want to use, You need an image dataset. The images for this project were found on Kaggle.com, which had a publicly available bike images dataset (partial dataset from DataCluster Labs).

Once here, I suggest following this amazing instructional video: https://www.youtube.com/watch?v=GRtgLlwxpc4
You will also need ultralytics yolov5 Google Collaboratory: https://github.com/ultralytics/yolov5/blob/master/README.md

### Step 2

It is recommended to split the images between training and validation training sets at this point.

Use makesense.ai to upload your images and train the dataset by drawing rectangles or other polygons around the objects you're hoping to detect. You can add as many labels as needed. Once created, you can export the annotations and upload them to the folder of your choice

### Step 3
Following the instructional video above, edit the yolov5 coco128.yaml file to point to your data and annotations.

### Step 4
Run the model however many times to maximize MAP_0.5 (which is the VOC metric used to determine accuracy as each image has an individual annotation.txt file) by varying batch and epoch size. Batch size refers to how many images are used to train the model during each run and epoch size refers to how many times the model is run over the training dataset. 

Batch size should typically be a multiple of 2 (16, 32, or 64 are typically good). Epoch size in this project had the most success around 60 or 120 epochs.

### Step 5
upload the testing video and run the model over the video. You can then export the detect video to visualize how well the model worked at detecting your desired object. You can change the confidence level of the model (--conf) to reduce the number of detected false positives.

### Tips
1. Depending on what type of object you are trying to detect and what the testing video is, it is best to train the model to recognize the expected orientation, use case, movement patterns, etc. that might be expected in the testing video. This is not saying to overfit the model or train the model based on the testing video. Rather, as what could have been done in this project, training the model on street camera footage (very granular, low resolution footage) with people riding bikes is more beneficial for training as compared to training the model on still images of bicycles of non-applicable orientations or which are not being ridden by cyclists.
