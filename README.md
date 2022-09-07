# About
This repository contain implementation of different Object Detection Algorithms. 
Object detection is a computer technology-related computer vision and image processing that deals with detecting instances of semantic objects of a certain class (such as humans, buildings, or cars) in digital images and videos. There are two terms that are used quite interchangeably when it comes to standard computer vision problems, object localization, and object detection. Predicting the class of a single object in a picture is known as image classification. The process of locating one or more items in an image and tracing a bounding box around their extent is known as object localization. These two tasks are combined in object detection, which locates and categorizes one or more things in an image.

Object localization is also known as simultaneous classification and localization where the goal of the model is to output what the object is and where it is whereas the only difference in object detection is that it handles the combinatorial nature of the world.
Object Detection = Image classification + Object localization.

# Techniques Used to built state-of-the-art object detection.
There have been many popular approaches for detecting objects. Amongst them, the popular ones which I am implementing are the Region proposal, regression and transformer approach models. Three different models are built to detect objects over 80 classes. 
## Regression-Based Model: YOLO
YOLO is a state-of-the-art, object detection algorithm. YOLO is an abbreviation for the term ‘You Only Look Once’ Joseph Redmon was the one who created it. The speed without much precision comprises is the major benefit over other designs. In comparison to R-CNN and other models, the YOLO family models learn relatively generic representations of the object quickly. By interpreting object detection as a single regression problem that spatially separates bounding boxes and associated class probabilities, YOLO avoids the need for complicated pipelines. YOLO directly optimizes detection performance while training on complete photos. It offers a single neural network that, in a single assessment, predicts bounding boxes and class probabilities from the entire image.
##	Region proposal Model: Faster RCNN
A team of researchers at Microsoft Faster 2015 created Faster RCNN the advanced version of R-CNN and Fast R-CNN which become the state-of-the-art object detection algorithm. RCNN stands for “Region proposal” combined with “Convolutional Neural Networks”. This is used to hypothesize object location in the regions proposed within the image. The region proposal algorithm seeks to replace the sliding window approach where the different regions are extracted from the image. These regions are then generally passed through the high-performance CNN to determine potential objects and their locations in the image. The RCNN Family model for object detection applies a convolutional neural network to further process extracted region to localize and segments objects. The version before Faster RCNN proposes approximately two thousand regions using a selective search technique per image which makes it slow enough when applied to large datasets. The computational bottleneck of the cutting-edge detection systems is observed to be region proposal techniques, which are observed to take as long as the detection network. As a result, the improved version known as Faster RCNN is created by removing the various phases involved in the prior procedure.
## Transformer Based model: DETR
The DETR model is an encoder-decoder transformer with a convolutional backbone. Two heads are added on top of the decoder outputs in order to perform object detection: a linear layer for the class labels and a MLP (multi-layer perceptron) for the bounding boxes. The model uses so-called object queries to detect objects in an image. Each object query looks for a particular object in the image. For COCO, the number of object queries is set to 100.
The model is trained using a "bipartite matching loss": one compares the predicted classes + bounding boxes of each of the N = 100 object queries to the ground truth annotations, padded up to the same length N (so if an image only contains 4 objects, 96 annotations will just have a "no object" as class and "no bounding box" as bounding box). The Hungarian matching algorithm is used to create an optimal one-to-one mapping between each of the N queries and each of the N annotations. Next, standard cross-entropy (for the classes) and a linear combination of the L1 and generalized IoU loss (for the bounding boxes) are used to optimize the parameters of the model.
# Learning
1. Better understanding of optimizers like Adam, Adagrad, RMSprop, SGD.
2. Usage of transformers for object detection.
3. New computer vision tools like Albumentations, OpenCV
# Challanges
To achieve state of the art, these models needs to be trained with large number of epochs to acheive maximum accuracy. I only train YOLO over 20 epochs and Faster RCNN over 5 epochs keeping the computational resources in mind.
