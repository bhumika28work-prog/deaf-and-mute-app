# Indian-sign-language-recognition

Hello, This repository contains python implementation for recognising Indian sign language (ISL) gestures. As there is less research, there is no standard dataset avialable in the web. So, we decided to create my own [dataset](https://drive.google.com/open?id=1keWr7-X8aR4YMotY2m8SlEHlyruDDdVi) of gesture images. ISL dataset have all alphabets (A-Z) and numerics (1-9) with total classes = 35. Each class has 1200 images. ISL gestures are practically hard to recognise as two hands are involved and because of complexity. To classify images, Bag-of-words (bow) model has been implemented with SVM. **70:30** ratio has been used for train and test to split. Using this method, the model gives 99% accuracy approximatly with very less error rate. 


## Gestures

All the gestures used in the dataset are in the shown below image with labels.

![image](all_gestures.jpg)

## Required setup
* python 2.7 (Does not work with upper versions as openCV does not support SURF features)
* opencv-python==3.4.2.16
* opencv-contrib-python==3.4.2.16
* numpy
* imutils

## Implementation

The implementation follows several steps:

i) Image segmentation (masking to get raw skin and edges in the image) <br/>
ii) SURF Feature detection (finding feature descriptors for all data) <br/>
iii) K-means clustering (Codebook generation: to cluster all features and to get visual words (bow)) <br/>
iv) Histograms computation (Using visual words (bow) compute histograms for each image) <br/>
v) SVM model for classification (input: histograms, output: predection for testdata) <br/>



