# face_recognition

Detect and recognize faces by simplest approach

I used [MTCNN](https://github.com/ipazc/mtcnn.git) as face detection and I used [FaceNet](https://arxiv.org/abs/1503.03832) approach. There are a number of projects that provide tools to train FaceNet-based models and make use of pre-trained models. 

I have used the pre-trained Keras FaceNet model provided by [Hiroki Taniai](https://github.com/nyoki-mtl) in this tutorial. It was trained on [MS-Celeb-1M](https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/) dataset and expects input images to be color, to have their pixel values whitened (standardized across all three channels), and to have a square shape of 160×160 pixels.


## Face detection

[Face detection](https://machinelearningmastery.com/how-to-perform-face-detection-with-classical-and-deep-learning-methods-in-python-with-keras/) is the process of automatically locating faces in a photograph and localizing them by drawing a bounding box around their extent.

In this project, I have also used the Multi-Task Cascaded Convolutional Neural Network, or MTCNN, for face detection, e.g. finding and extracting faces from photos. This is a state-of-the-art deep learning model for face detection, described in the 2016 paper titled “[Joint Face Detection and Alignment Using Multitask Cascaded Convolutional Networks](https://arxiv.org/abs/1604.02878).”

We have used the implementation provided by [Iván de Paz Centeno](https://www.linkedin.com/in/ivandepazcenteno/) in the [ipazc/mtcnn](https://github.com/ipazc/mtcnn) project. This can also be installed via pip as follows:

```python
!pip install ctnn
```

## Data 

In this project, We don't need many picture of specific person whereby we just need one picture. I have prepared database and test that they contain picture of 4 soccer player.

## Face Recognition

For this part, I have used FaceNet pre-trained [network](https://drive.google.com/open?id=1pwQ3H4aJ8a6yyJHZkTwtjcL4wYWQb7bn). This network extracts 128 dimensional that we call it embeded features. We store the embeded features of database pictures whenever we want recognize new picture, we compare new image embeded feature with database embeded features. Finally, we choose image among database images that it have most similarity with new image.
