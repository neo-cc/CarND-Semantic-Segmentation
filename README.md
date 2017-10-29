# Semantic Segmentation
### Introduction

##### Project Reprot
In this project, I labelled the pixels of a road in images using a Fully Convolutional Network (FCN). The model is based on VGG16 network with pre-trained value, by adding 1x1 convolutions, upsampling and skip layers to build the FCN. This FCN model for Semantic Segmentation is from [here](https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf).


[image1]: ./runs/1509298204.3174233/FCN.gif

AWS (instants type: `g3.4xlarge`, AMI: `udacity-carnd-advanced-deep-learning`) is used to train the FCN. There are only 4 hyper parameters. Originally I set Epochs 30, Batch Size 16, Learnign Rate 0.0005, the loss is around 0.15 after trainning. 

From 1st project sumbit review, it says
"Batch size used is on larger side. Try setting a value around 2 or 4.
We know that larger batch sizes might speed up the training but can degrade the quality of the model at the same time. Further, you'll need to reduce the number of epochs. Your epochs are on larger side, reduce it to ~15." 

After fine tune I decided to use following values the loss is around 0.04:
 
 - Epochs: 15
 - Batch Size: 4
 - Learning Rate: 0.0001
 - Dropouts(keep_prob): 0.5



The final output images are in `run/1509298204.3174233`

Below is the gif output:

![alt text][image1]


##### Debug: GPU not found on AWS:
```
TensorFlow Version: 1.2.1
2017-10-29 16:47:40.141479: E tensorflow/stream_executor/cuda/cuda_driver.cc:406] failed call to cuInit: CUDA_ERROR_NO_DEVICE
2017-10-29 16:47:40.141826: E tensorflow/stream_executor/cuda/cuda_diagnostics.cc:303] kernel version 375.66.0 does not match DSO version 384.90.0 -- cannot find working devices in this configuration
main.py:16: UserWarning: No GPU found. Please use a GPU to train your neural network.
  warnings.warn('No GPU found. Please use a GPU to train your neural network.')
```
To solve this:

```
sudo apt-get remove nvidia-*
wget http://us.download.nvidia.com/XFree86/Linux-x86_64/375.66/NVIDIA-Linux-x86_64-375.66.run
sudo bash ./NVIDIA-Linux-x86_64-375.66.run  --dkms
```
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
