## Project: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Data Set
---
In this project, I started with the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). The dataset consisted of 34799 training images of size 32 x 32 x 3 comprising 43 distinct classes, where each class corresponds to a different traffic sign. The dataset also has 4410 validation samples, and 12630 test samples. I preprocessed the RGB images into grayscale using the [luminosity](https://www.johndcook.com/blog/2009/08/24/algorithms-convert-color-grayscale/) method, and also normalized the values to be between [0,1]. The initial training samples were non-uniformly distributed amongst the various classes. 
![original dataset](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/histogram_original.png)

By random repetition, I augmented the training samples to have approx. 2000 training samples per class.
![augmented dataset](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/histogram_augmented.png)

The Network
---
I used the LeNet network architecture with minor changes to the output layer to provide a probability distribution over 43 classes instead of the traditional 10 classes.

![LeNet](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/LeNet.png)

### Dependencies
This lab requires:

* [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit)

The lab environment can be created with CarND Term1 Starter Kit. Click [here](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) for the details.

### Dataset and Repository

1. Download the data set. The classroom has a link to the data set in the "Project Instructions" content. This is a pickled dataset in which we've already resized the images to 32x32. It contains a training, validation and test set.
2. Clone the project, which contains the Ipython notebook and the writeup template.
```sh
git clone https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project
cd CarND-Traffic-Sign-Classifier-Project
jupyter notebook Traffic_Sign_Classifier.ipynb
```

### Requirements for Submission
Follow the instructions in the `Traffic_Sign_Classifier.ipynb` notebook and write the project report using the writeup template as a guide, `writeup_template.md`. Submit the project code and writeup document.
