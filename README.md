# Siamese-Network-Implementation-On-MNIST-Data-Using-Keras-

# Siamese Network Approach

The concept of **Siamese Network** and backpropagation using **Triplet Loss** approach was taken from [**FaceNet Paper**](https://arxiv.org/pdf/1503.03832.pdf)
, where it was immensely used for embedding of faces, where each face of the persons were pass through the model which gives 128 dimensional embedding array or an array of **128** values, which in turn compared with positive and negative image to calculate triplet losses and train the network model.

Let's go through the approaches stepwise with example:

* First we have a Convolutional Neural Network(CNN) Model

* Corresponding to each example there are three examples:

 1. person1_image1.jpg(Anchor example)
 2. person1_image2.jpg(Positive example)
 3. person2_image3.jpg(Negative example)

 ## **Siamese Network**

 * All the three images are passed through the model and we get three embedding for the three images(Anchor, Positive, Negative) corresponding to each example.
 * The three instances of the EmbedddingModel from the three images are shared instances of same model, i.e parameters are shared and are updated for the three paths simultaneously.
 
![Image1](https://github.com/sayan0506/Siamese-Network-Implementation-On-MNIST-Data-Using-Keras-/blob/master/Images/1_MIPdyhJGx6uLiob9UI9S0w.png)
[source](https://levelup.gitconnected.com/metric-learning-using-siamese-and-triplet-convolutional-neural-networks-ed5b01d83be3)

 The network architecture consists of three input images, are passes through a sequential network, which gives total 192 outputs(64 for each A, P, N type images) through a concatenated output layer. The Siamese Network structure is shown below:
 
![Image2](https://github.com/sayan0506/Siamese-Network-Implementation-On-MNIST-Data-Using-Keras-/blob/master/Images/model.png)

# Triplet Loss

A loss function that tries to pull the Embeddings of Anchor and Positive Examples closer, and tries to push the Embeddings of Anchor and Negative Examples away from each other.
Root mean square difference between Anchor and Positive examples in a batch of N images are calculated in that loss. Based on that loss Siamese Network is backpropagated, and tuned using Adam optimization technique. 

* The custom batches of triplets are created for training
* Triplets are trained for 10 epochs and 2048 batches
* After the training is done, 10 embeddings of 10 images corresponding to 10 digits are stores in a dictionary
* Then, random images from test data are picked and recognized using a difference function with the help of a threshold
* It performs with a decent accuracy, but more modification needed.

* The details implementation and calculations can be found in the **[Collab Notebook](https://github.com/sayan0506/Siamese-Network-Implementation-On-MNIST-Data-Using-Keras-/blob/master/Create_a_Saimese_Network_with_Triplet_Loss_in_Keras.ipynb)**

# Reference

* The project is inspired from Convolution Neural Network course of [Deep Learning Specialization Coursera](https://www.coursera.org/learn/convolutional-neural-networks/) by **Prof. Andrew Ng**.
* Florian Schroff, Dmitry Kalenichenko, James Philbin (2015). [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/pdf/1503.03832.pdf)
* Our implementation also took a lot of inspiration from the official FaceNet github repository: https://github.com/davidsandberg/facenet 


**All the contents are made public, and all modifications, pull requests are welcome but please open issue and discuss before executing any major change in the repository.**



