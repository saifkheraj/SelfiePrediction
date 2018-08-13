# SelfiePrediction

## 1.	Abstract

This project uses Selfie Image dataset to classify images into good and bad selfies. Also included in it is Neural Artistic Styles, Adversarial Networks and Deep Visualisation. I trained Convolutional Neural Network on Image dataset built on my own and then I went further and used Transfer Learning approach to classify images. Output of Model tells us images classified into good and bad selfies, also visualized gradient and each convolutional layer. I conclude on notes for future work.

## 2.	Introduction

I trained Convolutional Neural Network on Image dataset built on my own and then I went further and used Transfer Learning approach to classify images. There were different things needed to be done in this project which not only includes to classify images but also to enhance selfie of a particular person. Data Gathering took lot of time as I did that on my own. 


## 3.	Data

I wrote simple python code to gather images from internet using API, This gave me supervised dataset.


## 3. Related Work


Andrej had published on his experiment of what deep learning thinks about your selfie. That is one of the related work. He relied on the concept of transfer Learning to predict and visualise images that makes sense. He used Instagram as a source to gather training and test supervised images. He then used VGG Net with 1 layer connected layer to classify images. Paper on artistic Visual Arts is already published so I took direct reference from there. There was also work published on Feature Maximisation and Gradient Visualization so I used that too.


## 4. Methods and Models

I used different convolutional Neural Network architecture including one on my own, Inception and VGG Net to transfer learn..
I first used my own model to train convolutional neural network on small dataset which I built on my own using tensorflow. I built 3 layer convolutional neural network to overfit on training data just to check if the network is fine. I ran simple convolutional neural Network without adding any complexity( No batch normalisation). I first tested on validation data set on random weights which gave me accuracy of 53%. Then I ran optimization for some few iterations which resulted in 95% training accuracy. This clearly tells that network is learning. I also tested on unseen dataset.


I also did some gradient visualisation (feature maximisation approach) to visualised from first layer and later layers and updated noise image. 



I then used inception Model 2015 and transfer learn to classify into good and bad images. Inception Model is pertained on Image Net with lot of categories. I first tried on small dataset to just check out and make some kind of visualisation so I divided my data set into 3 parts Training set with 800 images and validation set with 200 images and test set with some few images initially.

I scaled all the images to 256x256x3 and used one hot encoding for labels due to tensorflow.



I then needed to process inception transfer values for training, validation and test images. For that I first needed to scale images between 0 and 255 because that is what inception model wants. Then I calculated transfer values for all the images which took so long time. For me it took more than an hour to compute transfer values. Transfer values are also known as bottleneck values, I  replaced layer in the inception model that does classification with own layer that does classification.

Transfer values are first saved in cache which calculates 2048 transfer value for all the images.

I also visualised transfer value for a particular image which I have done.


### Transfer Value Visualization

   Image to Show


Although this is not interpretable, may be for some classes some neutrons get activated which represents dark but that could be experimented. For better visualization, I used dimensionality reduction concept such as PCA and T-SNE to visualise in 2 dimensions.


### PCA Visualization

Image to Show

There are 2 classes which represents good and bad selfies. Data still does not look well clustered by applying PCA so I also tried applying T-SNE which is also one of the method of dimensionality reduction.



### T-SNE Visualization (Inception Model Transfer Values)


Image to Show 


Still so many overlapping can be seen but lets see how it works using Inception Model. Since I was working on tensorflow , I will need to make graph on top of inception model as we are doing tranfer learning.

We take placeholder of dimensions equal to transfer length because that is what we are taking as an input which is 2048 Dimensional input then we add fully connected layer of size 1024 and add softmax layer. We add optimizer to reduce loss. 

We take predictions from softmax layer and do computations for calculating accuracy.

Parameters:

Batch Normalization
Batch Size=64
Weight Initiliazation: Guassion From Tensorflow
Adam Optimizer

I tried different parameters but these above worked best for me.

During each iteration I added validation accuracy and use the saving model to use the best model with highest validation accuracy.



