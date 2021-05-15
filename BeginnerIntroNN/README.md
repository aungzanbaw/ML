# Beginner note for DeepLearning

## Sigmoid functions 
```
sigmoid = 1 / 1 + math.exp(-x)
```

## NN fun
```
prediction(D1, D2) = sigmoid((W1 * D1) + (W2 * D2) + B) 
# W = Weight
# D = Data
# B = Bias
```
## Cost fun
We can't change both data(later will filter, normalize, standardize) and prediction (w,b)
Our cost fun will accept prediction and ground truth
If cost fun over shoot the value, it will be positive number
If cost fun under shoot the value, it will be negative number
The learning, in this context refer to trying to get closer to the ground truth of target value in step manner
The learning rate, refer to how quickly we deduce or add
```
data + prediction => cost => minimize
```

## Squared Error
From discrete math, we know that if we squared something it's always positive
Random value of prediction need to get closer to target value e.g (5 - 5)<sup>2</sup> = 0
We calculate by slop of parabola(assume x is targeted data, y is predicted value)
Slope = Rise / Run in notation y = mx + b (m is slope)
If we have two point we can do m = Y<sub>2</sub> - Y<sub>1</sub> / X<sub>2</sub> - X<sub>1</sub>
Just like cost fun, negative slop is under value, positive slop is over value
```
(prediction-target) ** 2
```
If we combine above two, we got following, why cost? if we 
```
prediction = p,cost(p)
hypothesis = p+h, cost(p+h)
slope = cost(p+h) - cost(p) / p+h-p
slope = (cost(p+h) - cost(p)) / h
```
Cost(p) = (prediction - value)<sup>2</sup>
Cost(p+h) = (prediction + hypothesis - value)<sup>2</sup>
We can solve this by alge way we got this 2(prediction-value) 
By the *power rule* our cost fun (prediction-target)<sup>2</sup> will become (prediction-target)
## Running Rate 
Here we trying to get to the target point with 10% rate (step size)
```
step_size = 0.1
prediction = prediction - (step_size * slope(prediction)
```
## More cost fun
we can replace SeuqredError fun with cost, sin or sigmoid

## Linear regression
```y = mx + b```  here we will rename as "given x predict the value of y"
```y = w.x + b``` again w & b is only dynamic part, we can't modify anything (x)
We will change w & b, we are trying to predict y given x
We change b and interception of y will change 
We change w and slope will change 
We have predicted val & actual(truth) value, we will have ```predicted val - actual val```
We will use square error fun, SUM of n((predicted val - target val)<sup>2</sup>)
If we put 1/number of n (SUM of n((predicted val - target val)<sup>2</sup>)), we can called mean square error(MSE)

## SUM UP
Model y = mx + b
Error model(x) - target val)<sup>2</sup>

|   X   |   Y   | Model           | Error   |
| :---  | :---: | :-------------: | ------: |
| 1     | 2     | model(1) = 2.00 | e1 = model(1) - 2)<sup>2</sup> = 0.00 |
| 2     | 4     | model(2) = 2.83 | e2 = model(2) - 4)<sup>2</sup> = 1.36 |
| 3     | 5     | model(4) = 4.50 | e3 = model(4) - 5)<sup>2</sup> = 0.25 |

SUM(e1 + e2 + e3) = 1.61 (here we refer *learning* as getting this number as low as possible)
MSE = SUM(((w.x<sup>1</sup>+b) - 2)<sup>2</sup> + ((w.x<sup>2</sup>+b) - 4)<sup>2</sup> + ((w.x<sup>3</sup>+b) - 5)<sup>2</sup> + b)
2,4,5 are all target value, baise is include only once.

cost = diff<sup>2</sup>
diff = observed - predicted(target)
observed = sigmoid(Z)
Z = W<sup>1</sup>.X<sup>1</sup> + W<sup>2</sup>.X<sup>2</sup> + B

## Learning 
We need to get derivative of W<sub>1</sub> W<sub>2</sub> & B, then we sub/add from original (random weights and biase)
By repeatedly doing that our cost function will closer to zero and then we get the value of W and B