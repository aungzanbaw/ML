# Neural Networks and Deep Learning
This is the part of series from deeplearning.ai 

## Week1
1. Most of the DL booms come from
* computing power & specific hardwares like GPUs & TPUs
* huge data from daily usage of digital devices 
* new algorithms (ML concepts are not new)

2. DL thrive mostly on **supervised learning**
3. Pratically used on 
* Search 
* Recommendation
* Image recognition (tagging, categorizing, detection etc)
* Translation
* Text <=> Speech 
## Week 2 
N represent features<br>
M data size (prof andrew refer as training examples) M<sub>train</sub> M<sub>test</sub><br>
Logistic regression is for classification problem<br>
Weight would be N<sub>x</sub> dimensional vector & B would be real number (Prof mention that we won't use θ<sub>0</sub> as B & θ<sub>x</sub> as W)<br>
Lost fun compute the error for single training data set<br>
Cost fun compute average of the loss fun for entire training data set<br>
∂ is 'partial derivative' & d is for derivative with one para<br>
Time to refresh your calculus and computing graph<br>
Avoid explict for-loops and vectorization instead<br>
Back-propagation is nothing but the chain rule<br>
Rank 1 array is not row vector nor column vector<br>
Prof wants us to check using assert equal, to check correct array shape<br>
Linear Fun -> Activation Fun(proba) -> Loss(how much diff) -> Cost (sum total)

Notations<br>
  * X = R<sup>N<sub>x</sub> * M</sup>
  * Y = 1 * M
  * We read as given *X* what's the probability of Y (ŷ) in symbol we write **ŷ=P(y=1|X)** 0 <= ŷ <= 1 (we need activation fun)
  * X<sup>(i)</sup> Y<sup>(i)</sup> Z<sup>(i)</sup>, i refer to i-th of data
  * Given {(X<sup>(1)</sup>, Y<sup>(i)</sup>),.....} ŷ<sup>(i)</sup>≈y<sup>(i)</sup>
  *  **ŷ=σ(W<sup>T</sup>x+b)** where **σ(z)=1/1+e<sup>-(z)</sup>** if we solve that we got **σ(z<sup>(i)</sup>)=1/1+e<sup>-(W<sup>T</sup>x<sup>(i)</sup>+b)</sup>**
  * Instend of SE loss fun, we will use *l(ŷ,y) = -(y<sub>log</sub>ŷ+(1-y) <sub>log</sub>(1-ŷ))* it's for individual data set
  * Cost J (W,b) = 1/M Σ<sup>M</sup><sub>i=0</sub> l(ŷ<sup>(i)</sup>,y<sup>(i)</sup>) which become -1/M Σ<sup>M</sup><sub>i=0</sub> [y<sup>(i)</sup><sub>log</sub>ŷ<sup>(i)</sup> + (1-y<sup>(i)</sup>)<sub>log</sub>(1-ŷ<sup>(i)</sup>)] notice - minus in the front, [ ] for individual data, called "Cost of parameters w & b"
  * w := w - α (dJ(w)/dw), where α is learning rate and assume there is only w, same formula work for b
### Broadcasting example
[Broadcasting example](/NN_DL(coursera)/Week2/broadcast.ipynb)
### Programming exercie note 
Common steps for pre-processing a new dataset are:
* Figure out the dimensions and shapes of the problem  
* Reshape the datasets such that each example is now a vector of size (px * px * 3, 1)
* "Standardize" the data (divided by 255 maximum value of a pixel channel)

The main steps for building a Neural Network are:
1. Define the model structure (such as number of input features)
2. Initialize the model's parameters
3. Loop:
  * Calculate current loss (forward propagation)
  * Calculate current gradient (backward propagation)
  * Update parameters (gradient descent)
Often build 1-3 separately and integrate them into one function we call model()