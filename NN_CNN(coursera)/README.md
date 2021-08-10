* A convolution extracts features from an input image by taking the dot product between the input data and a 3D array of weights (the filter).
* The 2D output of the convolution is called the feature map
* A convolution layer is where the filter slides over the image and computes the dot product
* This transforms the input volume into an output volume of different size
* Zero padding helps keep more information at the image borders, and is helpful for building deeper networks, because you can build a CONV layer without shrinking the height and width of the volumes
* Pooling layers gradually reduce the height and width of the input by sliding a 2D window over each specified region, then summarizing the features in that region