
## Project: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Data Set
---
In this project, I started with the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). The dataset consisted of 34799 training images of size 32 x 32 x 3 comprising 43 distinct classes, where each class corresponds to a different traffic sign. The dataset also has 4410 validation samples, and 12630 test samples. 

I preprocessed the RGB images into grayscale using the [luminosity](https://www.johndcook.com/blog/2009/08/24/algorithms-convert-color-grayscale/) method, and also normalized the values to be between [0,1]. The conversion to grayscale reduces the dimensionality of the data. The conversion to grayscale and normalization reduces variability in the images from non-relevant factors such as lighting and shadows in the training set images. Normalizing all the dimensions equally is also a standard preprocessing step to ensure that the cost function is not dominated by a few dimensions which have larger magnitudes (but possibly lower information for the classification task) at the expense of other more relavant dimensions which may have smaller magnitudes (but contain more relavant information for classification).

The initial training samples were non-uniformly distributed amongst the various classes. This can cause the network weights to become biased towards detection of classes which have more training samples, at the expense of classes which are under-represented.
![original dataset](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/histogram_original.png)

For the network to train to a good set of weights that work well for detecting all classes I augmented the training samples to have approx. 2000 training samples for each class by random repetition.
![augmented dataset](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/histogram_augmented.png)

The Network
---
I used the LeNet network architecture with minor changes to the output layer to provide a probability distribution over 43 classes instead of the traditional 10 classes.

![LeNet](https://github.com/calvinhobbes119/Traffic-Sign-Classifier/blob/master/examples/LeNet.png)

Training, Validation and Testing
---
I trained the network on the augmented dataset using a batch-size of 128 samples, until the accuracy of the network on the validation set was in the range of (0.94, 0.95). I started with a learning rate of 0.001 which seemed to work well - so I did not touch this value. Typically the network accuracy converged to a value of around 0.95 within 50 epochs of training. But on very rare occassions I have to go upto 100 epochs to achive a validation accuracy of 0.95. Once the network achieved the above accuracy on the validation set, the code broke out of the training loop, and the network stopped training. Applying the trained network to the test dataset achieved an accuracy of 0.916. I also validated the network by downloading 5 traffic signs from the web. I specifically selected signs belonging to classes which had a higher representation in the training data. The network was able to correctly classify 4 out of the 5 signs, achieving an accuracy of 0.8.

Future improvements
---
I plan to experiment more using augmented dataset created from rotations, translations and jitter of the original training samples to make the network more robust. I also plan to improve the network using dropout regularization.
