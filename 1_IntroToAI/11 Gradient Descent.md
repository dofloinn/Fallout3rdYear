Basis for a learning algorithm for feedforward neural network

### <mark style="background: #69E7E4;">Learning with Gradient Descent</mark>

<mark style="background: #69E7E4;">MNIST database:</mark> Modified National Institute of Standards and Technology Database. A large DB of handwritten digits that is commonly used for training imaging processing systems

<mark style="background: #69E7E4;">MNIST dataset:</mark>
- comes in 2 parts
- 60,000 images to be used as training data. These images are scanned handwriting samples from 250 people, half of whom were US Census Bureau employees, and half of whom were high school students.
- images are greyscale and 28 by 28 pixels
- second part of the MNIST data set is 10,000 images to be used as test data from a different set of 250 people, used for testing the model

### <mark style="background: #69E7E4;">MNIST & Cost (Loss) Function:</mark>

Each training image x is 28 by 28 pixels and will be treated as a 784-dimensional input vector.

Desired output y = y(x), y is a 10-dimensional vector

E.g. if x depicts a 6, then y(x)=(0,0,0,0,0,0,1,0,0,0)T

Want an algorithm which lets us find weights and biases so that the output from the network approximates y(x) for all training inputs x.

<mark style="background: #69E7E4;">Use a cost function:</mark> 
![](https://i.imgur.com/FRMLwrt.png)

Known as quadratic cost function or <mark style="background: #69E7E4;">mean squared error</mark> or just <mark style="background: #69E7E4;">MSE</mark>

### <mark style="background: #69E7E4;">Cost Function:</mark>

When ``C(w,b)`` becomes small, i.e., ``C(w,b)≈0``, precisely when ``y(x)`` is approximately equal to the output, a, for all training inputs, ``x``.

Job of training algorithm is to find weights and biases so that ``C(w,b)≈0``

Or job of training algorithm will be to minimize the cost ``C(w,b)`` as a function of the weights and biases

Why not use number of images correctly classified by the network and try to maximise it?

For the most part, making small changes to the weights and biases won't cause any change at all in the number of training images classified correctly.

That makes it difficult to figure out how to change the weights and biases to get improved performance.

But with smooth cost function like the quadratic cost it turns out to be easy to figure out how to make small changes in the weights and biases so as to get an improvement in the cost.

### <mark style="background: #69E7E4;">Gradient Descent – simple version:</mark>

Assume for the moment that cost C depends on a single weight w

![](https://i.imgur.com/UMwDzdJ.png)
![](https://i.imgur.com/UXdT5Ue.png)

<mark style="background: #69E7E4;">Gradient Descent for single weight, no bias:</mark>
![](https://i.imgur.com/ufCjmdR.png)

Thus we iteratively adjust w by an amount proportional to the slope or gradient, but in the apposite direction. Then
- ``∆w = −η(dC/dw)`` where ``η (eta)`` the learning rate is a small constant ≥ 0
- ``∆C ≈ (dC/dw)∆w``
- ``∆C ≈ −η(dC)dw^2``

So ``∆C ≤ 0`` Thus, if we adjust w in the opposite direction if the gradient, the cost C will decrease as expected.

### <mark style="background: #69E7E4;">Gradient Descent:</mark>

Looks as if here the cost C(w, b) depends on a single weight and a single bias

In general, there could be thousands of weights and biases.

![](https://i.imgur.com/BmBne2N.png)

### <mark style="background: #69E7E4;">Multivariable Gradient Descent:</mark>

Cost C(w1, w2, ... w<sub>n</sub>, b) depends on many weights and a biases

The slope dC/dw is replaced by gradient vector

![](https://i.imgur.com/cphTPqF.png)

We will keep things simple by considering only two variables ``C v1, v2``

Then the gradient of C is 
![](https://i.imgur.com/8Lpcozm.png)

### <mark style="background: #69E7E4;">Minimising the cost function:</mark>

For sake of simplicity let us temporarily replace w and b with two variables v1 and v2.

Helps us to see what’s needed.

Find where C achieves its global minimum, need calculus

Slope or gradient tells us which way to go

What happens when we move the ball a small amount Δv1 in the v1 direction, and a small amount Δv2 in the v2 direction

![](https://i.imgur.com/8qyv9hB.png)

<mark style="background: #69E7E4;">Minimising the cost function with Partial Derivatives:</mark>

What happens to <mark style="background: #69E7E4;">C(v<sub>1</sub>,v<sub>2</sub>)</mark> when we adjust v<sub>1</sub> by a small amount Δv<sub>1</sub> and v<sub>2</sub> by a small amount Δv<sub>2</sub>?

Choose Δv<sub>1</sub> and Δv<sub>2</sub> so as to make ΔC negative.

Denote gradient of C by:
![](https://i.imgur.com/hsfu3vR.png)

### <mark style="background: #69E7E4;">Multivariable Gradient Descent</mark>

We adjust the vector v = (v1, v2) along the gradient ∇C but in the opposite direction. Same as in 1-D case.

∆v = −η∇C where η > 0

![](https://i.imgur.com/eaOD9HF.png)

which is a vector <mark style="background: #69E7E4;">dot product</mark>, so we rewrite as ΔC ≈ ∇C ∙ ∆v

We prefer vector notation as it can easily be done in Python

### <mark style="background: #69E7E4;">Multivariate Gradient Descent</mark>

ΔC ≈ ∇C ∙ ∆v

ΔC ≈ ∇C ∙ (−η∇C)

ΔC ≈ −η(∇C)<sup>2</sup>

Thus changing v = (v1, v2) in opposite direction to ∇C, leads to C decreasing as we saw in the single variable case.

### <mark style="background: #69E7E4;">Local Minima:</mark>

Computing the derivatives of C

We know now that learning consists of iteratively adjusting the network weights along the gradient ∇C until we get close to a cost minimum.

In general 
![](https://i.imgur.com/QQCowTi.png)

In particular
![](https://i.imgur.com/s13g06n.png)

So to compute ∆w, we need to compute all the partial derivatives of C for all weights in all layers, potentially a crippling computational burden.

### <mark style="background: #69E7E4;">Computing the Derivatives of C:</mark>

Good news is that there is an efficient way to do this known as backpropagation, found in chapter 2 of Nielsen

### <mark style="background: #69E7E4;">Cost or Loss Function C(w, b):</mark>

The cost function takes into account the difference between the desired output ``y`` and the actual output ``a`` for every input vector ``x``

![](https://i.imgur.com/JwfMgPw.png)

where ``n = number`` of training inputs. Average cost per input vector ``x``

![](https://i.imgur.com/pRLLbUB.png)

Then
![](https://i.imgur.com/OxV9FhC.png)

So the partial derivatives ``( ∂Cx / ∂wi )`` have to be computed for each weight w<sub>i</sub> and for each training input x.

Given that there could be 60,000 training input images as in MNIST, doing all these derivates 60,000 times would be prohibitive and learning would occur very slowly.

### <mark style="background: #69E7E4;">Stochastic Gradient Descent:</mark>

An idea called stochastic gradient descent can be used to speed up learning

Estimate the gradient ``∇C`` by computing ``∇Cx`` for a small sample of randomly chosen training inputs

By averaging over this small sample it turns out that we can quickly get a good estimate of the true gradient ``∇C``, and this helps speed up gradient descent, and thus learning.

Randomly pick out a small number m of randomly chosen training inputs. Label those random training inputs X1,X2,...,Xm, and refer to them as a mini-batch.

Provided the sample size m is large enough we expect that the average value of the ∇CXj will be roughly equal to the average over all ∇Cx , that is

![](https://i.imgur.com/IfhVuIV.png)

For example, if we have a training set of size n=60,000, as in MNIST, and choose a mini-batch size of m=10, this means we'll get a factor of 6,000 speedup in estimating the gradient.

<mark style="background: #69E7E4;">Then:</mark>
![](https://i.imgur.com/nuVNwl7.png)

Then recalling that

∆w<sub>i</sub> = −η(  ∂C /∂w<sub>i</sub> )

We can write:
![](https://i.imgur.com/Bd9Q67S.png)
