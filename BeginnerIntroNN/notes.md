# Beginner note for DeepLearning

## Sigmoid functions 
```
sigmoid = 1 / 1 + math.exp(-x)
```

## NN func
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
```
(prediction-target)<sup>2</sup>
```