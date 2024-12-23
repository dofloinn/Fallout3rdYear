### <mark style="background: #69E7E4;">Gradient Descent Recap:</mark>

For a single neuron with single input, no bias, 1 weight ``∆w = −η( dC/dw )`` where ``η (eta)`` the learning rate is a small constant ≥ 0

Then we can update the weight

``w = w + ∆w``

Or

``w = w − η( dC / dw )``

So we calculate the slope of C (gradient), use it to update w so that C gets smaller and repeat this process a number of times (called the epochs).

For general case of multilayer, multiple outputs, multiple inputs

``∆w = −η∇C``

![](https://i.imgur.com/ILb9S9A.png)

So to compute ∆w, we need to compute all the partial derivatives of C for all weights in all layers, potentially a crippling computational burden.

![](https://i.imgur.com/UK3Pfxc.png)

### <mark style="background: #69E7E4;">Computing the (∂C / ∂w<sub>i</sub> )</mark>

We will consider the case of a single sigmoid neuron with two inputs <mark style="background: #69E7E4;">x = (x1, x2)</mark> and desired output y.

![](https://i.imgur.com/DzD7umc.png)

### <mark style="background: #69E7E4;">Chain Rule:</mark>

C = 1/2(y − a)<sup>2</sup> here only a depends on the weights and bias

a = σ(z)

z = w<sub>1</sub>x<sub>1</sub> + w<sub>2</sub>x<sub>2</sub> + b here w<sub>1</sub>, w<sub>2</sub> and b are variables, x<sub>1</sub> and x<sub>2</sub> constants

How to calculate ( ∂C / ∂w<sub>1</sub>), ( ∂C / ∂w<sub>2</sub>) and ( ∂C / ∂b ) ?

Use the chain rule:
![](https://i.imgur.com/UONCWZk.png)

C = 1/2(y − a)<sup>2</sup>, a = σ(z), z = w<sub>1</sub>x<sub>1</sub> + w<sub>2</sub>x<sub>2</sub> + b

Similarly,  (∂C/∂w<sub>2</sub>) = a − y σ′(z) x<sub>2</sub>

and

![](https://i.imgur.com/05c6fWM.png)

We call the error (a-y) multiplied by derivative “delta“

``δ = a − y σ′(z)``

Then
![](https://i.imgur.com/tgAKgWL.png)


### <mark style="background: #69E7E4;">Sigmoid:</mark> 

![](https://i.imgur.com/eIJqoVG.png)

Nice thing about σ′z is that

![](https://i.imgur.com/kaJeRnk.png)

Then:
δ = (a − y)a(1 − a)

### <mark style="background: #69E7E4;">Perceptron Training:</mark>

Recall:
![](https://i.imgur.com/hCz9RzU.png)

Then:
![](https://i.imgur.com/Ssz3w8m.png)

∆w<sub>i</sub> and ∆b are computed many times and the weights and bias adjusted each time until we get close to a local minimum of C.

Gradual small steps in gradient descent


<mark style="background: #69E7E4;">Mean Squared Error (MSE) Cost Function</mark>

We only considered ∂C/∂w<sub>i</sub> for a single training input vector

Generally there are a number of them. Then we consider the gradient of average cost 
![](https://i.imgur.com/VzrmJ9C.png)
where C<sub>x</sub> is the cost associated with input vector x. Assume n training vectors.

Then:
![](https://i.imgur.com/fHn8aJo.png)

and
![](https://i.imgur.com/JnJJTrx.png)

### <mark style="background: #69E7E4;">In Python:</mark>

input vector of size n

epochs means the number of iterations

```Python
for ep in range(epochs):
	del_w = np.zeros((self.n,), dtype=float)
	del_b = 0.0
	# xs list of training vectors, ys list of outputs
	for x,y in zip(xs, ys):
		z = self.w.dot(x) + self.b
		a = sigmoid(z)
		delta = (a-y)*a*(1-a)
		
		del_w += delta * x
		del_b += delta
		
	del_w = -eta * del_w / len(xs)
	del_b = -eta * del_b / len(xs)
	
	self.w += del_w
	self.b += del_b
```