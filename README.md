# Siamese-Network-Implementation-On-MNIST-Data-Using-Keras-

# Siamese Network Approach

The concept of **Siamese Network** and backpropagation using **Triplet Loss** approach was taken from **FaceNet Paper**, where it was immensely used for embedding of faces, where each face of the persons were pass through the model which gives 128 dimensional embedding array or an array of **128** values, which in turn compared with positive and negative image to calculate triplet losses and train the network model.

Let's go through the approaches stepwise with example:

* First we have a Convolutional Neural Network(CNN) Model

* Corresponding to each example there are three examples:

 1. person1_image1.jpg(Anchor example)
 2. person1_image2.jpg(Positive example)
 3. person2_image3.jpg(Negative example)

 ## **Siamese Network**

 * All the three images are passed through the model and we get three embedding for the three images(Anchor, Positive, Negative) corresponding to each example.
 * The three instances of the EmbedddingModel from the three images are shared instances of same model, i.e parameters are shared and are updated for the three paths simultaneously.
