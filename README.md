# Build-a-cat-breed-image-classification-model-with-the-Inception-CNN-architecture
 A typical Convolution Neural Network (CNN) is made up of stacked convolution layers in combination with max pooling and dropout. In a CNN layer we make a choice to either have a stack of 3x3 filters or a stack of 5x5 filters or a max pooling layer. All these are beneficial to the modelling power of the network. The inception module suggests to use all. These means instead of adding a particular filter layer we add all 1x1, 3x3 and 5x5 layer. The output of all the filters is concatenated and passed onto the next layer. 
  
The dataset is of 10 breeds of cats: Bombay, Calico, Burmese, Himalayan, Munchkin, ragdoll, Siberian, British shorthair, Russian Blue, Dilute Calico.  We will train the architecture on this dataset consisting of 10 different classes.  Each image is represented as 32x32 pixels each for red, blue and green channels. The labels are converted to categorical type using one hot encoding, dataset is split into training and testing sets. Image size is kept constant and all these tasks are carried by “image_dataset_from_library” from the TensorFlow library.  

In order to create a model, let us first decide an input_img tensor as 32x32 image with 3 channels (RGB). We will create 1x1, 3x3, 5x5 Convolution layers for the inception model. We will provide input_img tensor to layer_1, layer_2, layer_3.  The padding is kept same so that the output shape of the Conv2D operation is same as the input shape. So, the final output of each filter of layer_1, layer_2 and layer_3 is same. Thus, we can easily concatenate these filters to form the output of our inception module. We flatten the output to a one-dimensional collection of neurons which is then used to create a fully connected neural network as a final classifier.  

Thus, we obtain a fully connected neural network with final layer having 10 neurons one corresponding to each class. We can now create the model we compile and fit the model with RMSprop optimizer.  
