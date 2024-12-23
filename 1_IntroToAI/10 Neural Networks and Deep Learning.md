### <mark style="background: #69E7E4;">Learning:</mark>

Can <mark style="background: #69E7E4;">devise learning algorithms</mark> which can automatically tune the weights and biases of a network of artificial neurons.

this tuning happens in response to external stimuli, without direct intervention by a programmer.

These learning algorithms enable us to use artificial neurons in a way which is radically different to conventional logic gates.

Instead of explicitly laying out a circuit of NAND and other gates, our neural networks can simply learn to solve problems, sometimes problems where it would be extremely difficult to directly design a conventional circuit.

### <mark style="background: #69E7E4;">Sigmoid Neurons:</mark>

How to obtain a learning algorithm?

Suppose we make a small change in some weight (or bias) in the network. What we'd like is for this small change in weight to cause only a small corresponding change in the output from the network.

![](https://i.imgur.com/nmZNtbr.png)

Could figure out how to make a small change in the weights and biases so the network gets a little closer to classifying the image as a "9". And then we'd repeat this, changing the weights and biases over and over to produce better and better output. The network would be learning.

Not what happens with perceptrons

Small change in the weights or bias of any single perceptron in the network can sometimes cause the output of that perceptron to completely flip, say from 0 to 1.

That flip may then cause the behaviour of the rest of the network to completely change in some very complicated way.

Hard to see how small changes can lead gradually to solution.

We can overcome this problem by introducing a new type of artificial neuron called a sigmoid neuron. Same notation as before.

Instead of being just 0 or 1, these inputs can also take on any values between 0 and 1

Output is not 0 or 1. Instead, it's ``σ(w⋅x+b)``, where σ is called the sigmoid function.

![](https://i.imgur.com/97wraS6.png)

### <mark style="background: #69E7E4;">Sigmoid Function:</mark>

![](https://i.imgur.com/uPu37Ua.png)

### <mark style="background: #69E7E4;">Sigmoid & Step (Heaviside) functions:</mark>

Many similarities between perceptrons and sigmoid neurons.

Suppose ``z=w⋅x+b`` is a large positive number. Then e<sup>−z</sup>≈0 and so ``σ(z)≈1``.

Suppose on the other hand that z=w⋅x+b is very negative. Then e<sup>−z</sup>→∞, and ``σ(z)≈0``.

![](https://i.imgur.com/puJj3hN.png)

### <mark style="background: #69E7E4;">Perceptron versus Sigmoid Neuron:</mark>

![](https://i.imgur.com/c40OfmJ.png)

### <mark style="background: #69E7E4;">Sigmoid Neuron:</mark>

By using the actual σ function we get, as already implied above, a smoothed out perceptron.

Then for neuron with a single input and no bias, a small variation in weight Δw results in a small change to the output, approximately given by:

![](https://i.imgur.com/Kd8HVVl.png)

<mark style="background: #69E7E4;">For multiple weights and bias</mark>, partial derivatives are required:

![](https://i.imgur.com/gFLBlOL.png)

Δ output is a <mark style="background: #69E7E4;">linear function</mark> of the changes Δwj and Δb in the weights and bias. This linearity makes it easy to choose small changes in the weights and biases to achieve any desired small change in the output.

So while sigmoid neurons have much of the same qualitative behaviour as perceptrons, they make it much easier to figure out how changing the weights and biases will change the output.

### <mark style="background: #69E7E4;">Activation Functions:</mark>

Refer to σ as the activation function.

<mark style="background: #69E7E4;">Can use many others:</mark>
![](https://i.imgur.com/9UQi0Go.png)

<mark style="background: #69E7E4;">Partial derivatives are important</mark>

Turns out that when we compute those partial derivatives later, using σ will simplify the algebra.

Suppose we want the output from the network to indicate either "the input image is a 9" or "the input image is not a 9”. More like what perceptron does. But!

### <mark style="background: #69E7E4;">Architecture of neural network:</mark>

![](https://i.imgur.com/aSKaKBd.png)

The design of the input and output layers in a network is often straightforward.

For example, suppose we're trying to determine whether a handwritten image depicts a "9" or not.

A natural way to design the network is to encode the intensities of the image pixels into the input neurons. If the image is a 64 by 64 greyscale image, then we'd have 4,096=64×64 input neurons, with the intensities scaled appropriately between 0 and 1.

The output layer will contain just a single neuron, with output values of less than 0.5 indicating "input image is not a 9", and values greater than 0.5 indicating "input image is a 9 ".

While the design of the input and output layers of a neural network is often straightforward, there can be quite an art to the design of the hidden layers.

Not possible to sum up the design process for the hidden layers with a few simple rules of thumb.

Instead, neural networks researchers have developed many design heuristics for the hidden layers, which help people get the behaviour they want out of their nets.

### <mark style="background: #69E7E4;">Simple Network to classify handwritten digits:</mark>

![](https://i.imgur.com/BESo9CN.png)

<mark style="background: #69E7E4;">Segmentation:</mark>
![](https://i.imgur.com/EgV9xgm.png)

Not easy for a computer program to do, human doesn’t even think
about it.

<mark style="background: #69E7E4;">Design:</mark>
![](https://i.imgur.com/pJiG8Fc.png)

### <mark style="background: #69E7E4;">10 versus 4 output neurons:</mark>

Why not just use 4 output neurons? 2^4 = 16, which would cover all 10 possibilities.

Suppose that the first neuron in the hidden layer detects whether or not an image like the following is present

Heavily weighting input pixels which overlap with the image, and only lightly weighting the other inputs.

In a similar way, let's suppose that the second, third, and fourth neurons in the hidden layer detect whether or not the following images are present:
![](https://i.imgur.com/d0MiK0b.png)

![](https://i.imgur.com/plhXlTp.png)

So if all four of these hidden neurons are firing then we can conclude that the digit is a 0.

If we had 4 outputs, then the first output neuron would be trying to decide what the most significant bit of the digit was. And there's no easy way to relate that most significant bit to simple shapes like those shown above.

This is all just a heuristic. Nothing says that the three-layer neural network has to operate in the way described.

### <mark style="background: #69E7E4;">Could have 4-bit output layer:</mark>

![](https://i.imgur.com/60FhWui.png)
