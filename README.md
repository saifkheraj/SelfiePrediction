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


