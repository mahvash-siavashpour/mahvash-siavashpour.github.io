---
layout: page
title: Handwritten Digit Recognition
description: Implementation of a FCNN from scratch through mathematical calculations
img: assets/img/digit-recognition.png
importance: 3
category: AI
---

One of the most famous machine learning and computer vision tasks is handwritten digit recognition. One can use multiple libraries to do this job, but in this project the neural network is implemented from scratch and trained for handwritten digit recognition task. 


## Implementation of the ANN
To implement this network, I used 28*28 = 784 neurons in the first layer, each representing a single pixel in the input image. There are also ten neurons in the last layer, one neuron for every digit. Finally, there are two hidden layers with sixteen neurons each.
I implemented the learning phase using the pseudo-code below:
<br>
<img src="assets/img/sudo-code.png" alt="sudo-code"  width="450"/>
{% include figure.html path="assets/img/sudo-code.png" title="example image" class="img-fluid rounded z-depth-1" %}
<br>
In order to train the network, we first need to get the appropriate dataset. I used the MNIST dataset containing 60,000 handwritten digit images in the train section and 10,000 more in the test section.
<br>
<img src="assets/img/digits.png" alt="digits"  width="450"/>
<br>
As illustrated above, the digits are in a 28*28 pixel image with a black background. Each pixel has a value between 0 to 255 showing how bright it is. I divided these values by 255 to scale them between 0 to 1 and that is the input to the neuron responding to that pixel.
After acquiring the images, we can feed them into the ann using the feedforward method. After that we can calculate the cost function and adjust the weights using the backpropagation.

## RESULTS AND CONCLUSION
For testing the network, the First thing is to create our wights and biases matrices randomly and to calculate the accuracy before doing ant training on the network. Next we train our network by feeding the first 100 images into the neural network from our train set and then training it by backpropagation.
Here are the parameters I used to train the network, the accuracy and the results:
<br>
<img src="assets/img/mnist-table.png" alt="table"  width="450"/>
<br>
The following plot shows the cost function output in each epoch of training the ann:
<br>
<img src="assets/img/plt1.png" alt="plot1"  width="450"/>
<br>
I tested the results with 200 epochs and 500 samples and the final accuracy increased by more than 10 percent. I also did the same test with the hyperbolic tangent as the activation function. The ploting of each of these tests are illustrated below:
<br>
<img src="assets/img/plt2.png" alt="plot2"  width="450"/>
<br>