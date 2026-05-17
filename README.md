# Part 2: CNN Prototype for Manufacturing Defect Classification

## Project Overview
In this project, I built a basic Convolutional Neural Network (CNN) to classify
manufacturing surface images into one of four categories:

- *normal*
- *scratch*
- *dent*
- *stain*

The objective of this assignment is to understand how CNNs learn visual patterns
from image data using convolution layers, activation functions, pooling layers,
flattening, and dense layers.

---

## Problem Identification
This dataset represents an *image classification* problem.

### Why image classification?
Each image in the dataset has exactly *one class label*.  
There are no:
- bounding boxes
- object coordinates
- segmentation masks

So the model needs to assign one label to the full image, which makes this a
multi-class image classification task.

---

## Dataset Summary
The dataset contains *480 images* across *4 classes*:

- normal → 120 images
- scratch → 120 images
- dent → 120 images
- stain → 120 images

This means the dataset is *balanced*, which is useful because the model is not
biased toward any one class.

---

## Tasks Covered
The notebook includes the following:

1. Problem identification
2. Dataset exploration
3. Image preprocessing
4. CNN model creation
5. Model training and evaluation
6. CNN concept explanation
7. Business use case mapping

---

## Dataset Exploration
The following checks were performed:
- number of classes
- number of images per class
- sample images from each class
- image dimensions
- class balance analysis

---

## Image Preprocessing
Before training the CNN, the following preprocessing steps were done:

- resized all images to a fixed size
- normalized pixel values to the range *[0, 1]*
- split the data into *training, **validation, and **test* sets
- applied light data augmentation

---

## CNN Model Architecture
A simple CNN model was built using TensorFlow/Keras with the following layers:

- Convolution layer
- ReLU activation
- Max pooling layer
- Flatten layer
- Dense layer
- Softmax output layer

This model is suitable for a small image classification prototype.

---

## Model Evaluation
The model was evaluated using:

- training accuracy and loss
- validation accuracy and loss
- test accuracy
- confusion matrix
- sample predictions on test images

Result files are saved in:
- results/
- sample_predictions/

---

## CNN Concepts in Simple Terms

### What is convolution?
Convolution is the process of applying small filters over an image to detect
patterns such as edges, shapes, textures, or defects.

### Why is pooling used?
Pooling reduces the size of feature maps. This makes the model faster and helps
it focus on the most important visual information.

### Why is ReLU commonly used in CNNs?
ReLU is simple, efficient, and helps the network learn non-linear patterns.
It also works well in deep learning models because it speeds up training.

### Why are CNNs better than regular feed-forward networks for image data?
CNNs are better for images because they preserve spatial structure and learn
local visual patterns. Feed-forward networks flatten the image too early and
lose that important spatial information.

---

## Business Use Case Mapping
This type of computer vision solution is highly useful in *manufacturing*.

In a real production environment, product images can be captured using cameras
and passed through a CNN model to automatically identify whether the product is:

- normal
- scratched
- dented
- stained

This helps companies:
- reduce manual inspection effort
- improve consistency in quality control
- detect defects early
- reduce rework and waste
- improve customer satisfaction

So this project can be directly mapped to automated quality inspection in manufacturing.

---

## Repository Structure
part-2-cnn-computer-vision/
│
├── README.md
├── notebook.ipynb
├── requirements.txt
├── labels.csv
├── images/
│   ├── normal/
│   ├── scratch/
│   ├── dent/
│   └── stain/
├── sample_predictions/
│   └── prediction_outputs.png
└── results/
    ├── accuracy_loss_curves.png
    └── confusion_matrix.png
