# HandWritten Digit Recognition by Neural Network from Scratch 
In this project, I developed an ANN framework from scratch which can use to train and evalute Fully Connected Neural Network for different task. I use this framework to train an ANN model for ```Handwritten Digit Recognition``` Task, which is one of the most famous machine learning and Computer Vision tasks. 

## Table of Contents
* [Dataset](https://github.com/MohammadJavadArdestani/Data-Mining-projects/edit/main/Diabetes_detection_by_XGBoost_Classifier/README.md#dataset)
* [ANN Framework](https://github.com/MohammadJavadArdestani/Data-Mining-projects/edit/main/Diabetes_detection_by_XGBoost_Classifier/README.md#preprocessing)
* [HandWritten Digit Recognition](https://github.com/MohammadJavadArdestani/Data-Mining-projects/edit/main/Diabetes_detection_by_XGBoost_Classifier/README.md#xgboost-model)
* [Adversarial Attack by Shifting Digit Pattern Matrices](https://github.com/MohammadJavadArdestani/Data-Mining-projects/edit/main/Diabetes_detection_by_XGBoost_Classifier/README.md#xgboost-model)

## Dataset
The MNIST dataset is used in this project. For more datails click [Here](http://yann.lecun.com/exdb/mnist/).

## ANN Framework
Adaptable architecture for Feed-forward Fully Connected Neural Network is implemented. You can change the number of cells, hidden layers, Loss function and the activation function to customize the ANN model for your task.<br><br>

You can define model's architecture by changing following parameters:
```bash
layers_num = 3 
input_size = [28*28] 
hidden_layers_size = [16, 16]
output_size = [10]
```
You can use following activation functions for your model: 

   * Linear
   * Sigmoid
   * Relu
   * Leaky_relu
   * Tanh <br><br>

Forward and Backward phases are implemented in two different approch for comparison of memory consumption and runtime: <br>
 *  Elementwise method by ```For loop``` iteration 
 *  ```NumPy``` Vectorization <br>
 
I trained an ANN by 100 samples of data. The elementwise method Took about 136s for 20 Epochs but vectorized needed 13.4 to train the model over 200 epochs.<br> So the vectorized approach decreases the training time dramatically. 

 ## HandWritten Digit Recognition
 
An ANN model defined by following Architucture: 
```bash
layers_num = 3
input_size = [28*28] 
hidden_layers_size = [16, 16]
output_size = [10]
```
This model trained by this parameter and reached  about 91% accuracy for train and test dataset. 

```bash
train( epoch_num = 5,
       batch_size = 50,
       train_data = train_set,
       learning_rate = 0.01,
       vectorized = 1,
       activation_func = sig,
       activation_derivative = sig_derivative) 
```

## Adversarial Attack by Shifting Digit Pattern Matrices
Images had been shiffted 4 pixels to the right
![shifting process](https://github.com/MohammadJavadArdestani/HandWritten-Digit-Recognition-by-Neural-Network/blob/main/Capture.PNG) <br>
The model's accuracy falls below 30% because of shifting the data to just 4 pixels, which is a considerable amount of vulnerability.
