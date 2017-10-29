# Semantic Segmentation
### Introduction
In this project, I labelled the pixels of a road in images using a Fully Convolutional Network (FCN). The model is based on VGG16 network with pre-trained value, by adding 1x1 convolutions, upsampling and skip layers to build the FCN. This FCN model for Semantic Segmentation is from [here](https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf).


[image1]: ./runs/1509253607.271929/FCN.gif

AWS (instants type: `g3.4xlarge`, AMI: `udacity-carnd-advanced-deep-learning`) is used to train the FCN. There are only 4 hyper parameters, and after fine tune I decided to use following values:
 
 - Epochs: 30
 - Batch Size: 10
 - Learning Rate: 0.0005
 - Dropouts(keep_prob): 0.5

The final output images are in `run/1509253607.271929`

Below is the gif output:

![alt text][image1]

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
