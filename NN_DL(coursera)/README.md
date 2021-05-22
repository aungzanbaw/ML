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
Weight would be N<sub>x</sub> dimensional vector & B would be real number (Prof mention that we won't use θ<sub>0</sub> as B & θ<sub>x</sub> as W)
Notations<br>
  * X = R<sup>N<sub>x</sub> * M</sup>
  * Y = 1 * M
  * We read as given *X* what's the probability of Y (ŷ) in symbol we write **ŷ=P(y=1|X)** 0 <= ŷ <= 1 (we need activation fun)
  * X<sup>(i)</sup> Y<sup>(i)</sup> Z<sup>(i)</sup>, i refer to i-th of data
  * Given {(X<sup>(1)</sup>, Y<sup>(i)</sup>),.....} ŷ<sup>(i)</sup>≈y<sup>(i)</sup>
  *  **ŷ=σ(W<sup>T</sup>x+b)** where **σ(z)=1/1+e<sup>-(z)</sup>** if we solve that we got **σ(z<sup>(i)</sup>)=1/1+e<sup>-(W<sup>T</sup>x<sup>(i)</sup>+b)</sup>**
  * Instend of SE loss fun, we will use *l(ŷ,y) = -(y<sub>log</sub>ŷ+(1-y) <sub>log</sub>(1-ŷ))*
  * Cost J (W,b) = 1/M Σ<sup>M</sup><sub>i=0</sub> l(ŷ<sup>(i)</sup>,y<sup>(i)</sup>) which become -1/M Σ<sup>M</sup><sub>i=0</sub> [y<sup>(i)</sup><sub>log</sub>ŷ<sup>(i)</sup> + (1-y<sup>(i)</sup>)<sub>log</sub>(1-ŷ<sup>(i)</sup>)]