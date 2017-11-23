Semantic Segmentation Project (Advanced Deep Learning)
=========================================

introduction
--------------------------
The goal of this project is creating the model of fully convolutional neural network which identify the space of the road in an image feed to network.

Approach
---------------------------
### Architecture
For construct fully convolutional neural network, pre-trained VGG16 network is used.  
The output of this pre-trained network is converted to 1x1 convolutional layer and feed to next convolutional transpose layer.  
And for improvement of performance, 1x1 convolution of layer4 is added.  
And then to construct next layer, convolutional transpose is used and 1x1 convolution of layer3 is added.  
And next transpose convolutional layer is final output.
In each layer, kernel initializer and regularizer is used.

### loss function
To generate loss, soft max cross entropy is used.  
And in training, adam optimizer is used for optimize.

### Training
The hyperparameters used for training are:  
keep_prob: 0.5  
    learning_rate: 0.0009  
    epochs: 50  
    batch_size: 5

### Result
At epoch 50, The loss becomes about 0.032 to 0.015.


The following is from the original Udacity repository README
=========================================
### Introduction
In this project, you'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder  (**all images from the most recent run**)

 ## How to write a README
A well written README file can enhance your project and portfolio.  Develop your abilities to create professional README files by completing [this free course](https://www.udacity.com/course/writing-readmes--ud777).
