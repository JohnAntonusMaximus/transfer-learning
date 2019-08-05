# Transfer Learning & Fine Tuning w/ MobileNetV2 - TensorFlow 2.0 

[![Tensorflow](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7b9ZDD7lMdkByT-f_RCAqSQYqnq_CpgD16IFrwfmUwWCmdt7H)](https://www.tensorflow.org/beta/guide/effective_tf2)

[![Colab](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/github/JohnAntonusMaximus/transfer-learning/blob/master/Transfer_Learning_%26_Fine_Tuning.ipynb)

## Background

Transfer learning is using a pre-trained machine learning model as a basis for training a custom machine learning model. The model is imported and frozen 
while adding custom input and output layers to create a new model for a specific task. In this example, I'm using MobileNetV2 as a pretrained model, and
then adding a custom binary classification output layer for classifying pictures as a cat or a dog. 

The original dataset can be found here:
https://storage.googleapis.com/mledu-datasets/cats_and_dogs_filtered.zip


## Labels (Binary Classification)

Each picture can be classified as either a cat or a dog, so we have one output neuron in the final layer with a sigmoid activation function.							

## Approach

Using MobileNetV2, we import the model and freeze the weight, we then add a Global Average Pooling layer to make sure the output shape from the final layer in MobileNetV2 matches our input shape to the final prediction layer. We could flatten the image and then pass it, but the images are quite large here. We're also using Data Generators to resize the images as they are fed into the network during training and validation. Because mobile net is a
large and highly trained network, we get need state-of-the-art accuracy on the second epoch (100% accuracy), with validation tests very high as well (95%)

Later on in the notebook, we unfreeze the first 100 layers of Mobile net to do some fine tuning for our specific cat-dog binary classifier to see if we
can improve our accuracy even more. In this case, fine tuning actually caused overfitting on the training data, and validation results were worse, so 
for this example, fine tuning isn't really necessary. 


# Links

* [KaizenTek](http://www.kaizentek.io) - IT Consulting & Cloud Professional Services  



