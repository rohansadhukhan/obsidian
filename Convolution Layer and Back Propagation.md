
As you may think (article)


Perceptron - Iterative algorithm to learn the weight vector. Update weights in proportion to the error contributed by inputs.

Steps 

Randomly initialise the weight vector $\vec{W_0}$ 
Repeat until error is less than a threshold $\gamma$ or max iteration $M$ 
For each training sample we have $(\vec{x_i}, t_i)$ where $\vec{x_i}$ is the input vector and $t_i$ is the labeled output. Predict output $y_i$ using current network weights $\vec{W_n}$ and updates the weight vector as 
$$\vec{W_{n+1}} = \vec{W_n} + \eta * (t_i - y_i) * x_i$$
where $\eta$ is the learning rate and $(t_i - y_i)$ is the error

When we need Deep Learning ?
Where inputs are very raw and not able to extract features. This requires large number of data and more compute.



Multi Layer Perceptron (MLP)

Why we need this ?
Single neuron acts as a linear classifier 

Back Propagation
Steps
Forward Pass
Compute Loss
Backward Pass
Weight Update

Loss Functions -> Cross Entropy (CE) and Categorical Cross Entropy (CCE)


## Convolution Layer

Shared weights and sparse connectivity (not every neuron connected to all other neuron)