# Customer Churn Prediction <br >
## Machine Learning Recap: <br >
- Feature : Feature means measurable properties in training datasets. For example, in house rent prediction in apartment, features can include square footage, number of bedrooms and bathrooms, year built, and location. <br >
- Numerical Vector Representation : Numerical vector representation is a numeric form (a ordered number list) of data after embedding the original data. Machine learning models only accepts numeric data, so transforming non-numeric data into numeric vector representation is part of data preprocessing before training models using those data. <br >
- Embedding : Embedding means transform original data to numerical vector representation. <br >
- one-hot encoding : One-hot encoding means gives each categorical label one vector class to represent it's category. e.g. to represent cat, dog, bird, <br >
  - cat = [1, 0, 0], dog = [0, 1, 0], bird = [0, 0, 1] <br >
- __X__ , __y__ , __X\_train__ , __y\_train__ , __X\_test__ , __y\_test__ :
  - __X__ means features, inputs like __questions__ we give the model to make predictions. <br >
  - __y__ means labels, outputs like __answers__ we give the model to compare if the model predictions are correct. <br >
  - __X\_train__ are the datasets (questions) we give the model in __Training Phase__ to let the model make predictions. <br >
  - __y\_train__ are the labels (answers) we give the model in __Training Phase__, so the model can compare and __update weights__. <br >
  - __X\_test__ are the datasets (unseen questions before) we give the model in __Test Phase__ to let the model make predictions. <br >
  - __y\_test__ are the labels (ground truth answers) we give the model in __Test Phase__ to let the model check __how well the predicitons are__ after training phase. <br >
- epochs : Epochs means how many time the full training dataset pass through the model. For example, epochs = 50 means the model will train with that dataset 50 times. <br >
- batch_size : Batch size means how many samples the model will process at once. For example, batch_size = 128 means the model will process 128 samples at a time in the full training dataset, then update weights. <br >
- step : Step means how many time the model will update weights during training. <br >
  $`steps\_per\_epoch = number\_of\_samples\_in\_training\_dataset / batch\_size`$ <br >
  $`total\_steps = number\_of\_epochs * steps\_per\_epoch`$ <br >
  In training: $`how\_many\_time\_the\_model\_will\_update\_weights = total\_steps = number\_of\_epochs * number\_of\_samples\_in\_training\_dataset / batch\_size`$ <br >
- evaluate : Evaluate means after model trains with training dataset, we feed the model test dataset (dataset the model didn't see before) for prediction and measure how good the trained moded is. <br >
- history : History is a log object contains training metric (loss, accuracy) for each epoch and validation metric. When I train a model with training dataset, it returns a history object which I can draw learning curve, e.g. loss vs. epochs, accuracy vs. epochs. <br >

## Machine Learning Library:
- `sklearn.model_selection.train_test_split(*arrays, test_size=None, train_size=None, random_state=True, shuffle=True, stratify=True)`<sub>[1]</sub>: `train_test_split()` is a common tools for spliting original dataset into train set and test set. The `*arrays` is not an argument. Instead, `*` means one or more, so `*arrays` means the function accepts one or more arrays to be split. <br >
- `sklearn.preprocessing.StandardScaler()`<sub>[2]</sub>: The `StandardScaler()` creates scaler object to scale features. After creating scaler object, I can call `fit()` and `transform()`. <br >
  - Why do I need `StandardScaler()`? I need to make features from X_train set into same scale because different features can have different scales, e.g. __Age__ = 1\~80, __Month\_Spend__ = 0\~5,000. If I don't scale features, the ML models will treat __Month\_Spend__ as more important feature because it has higher number than __Age__. <br >
  - `StandardScaler.fit()`: It goes over features in X_train set and computes and stores mean (μ) and standard deviation (σ) for each features for standardization later. <br >
  - `StandardScaler.transform()`: With mean (μ) and standard deviation (σ) for each features, it applies standaraization to the data:<sub>[3]</sub><br >
  $`x_{scaled} =  \frac{x-μ}{σ}`$<br >
  - `StandardScaler.fit_transform()`: The StandardScaler do `fit()` and `transform()` at once. <br >
  - Common usage: <br >
  ```Python
  scaler = sklearn.preprocessing.StandardScaler()     #declare StandardScaler()
  X_train_scaled = scaler.fit_transform(X_train)    #get mean and standard deviation from X_train set and apply standardization on X_train set
  X_test_scaled = scaler.transform(X_test)          #apply standardization on X_test set (unseen feature/data remains unseen) with the same mean and standard deviation from X_train set
  ```
- `tensorflow.keras.Sequential()`<sub>[4]</sub>: The `Sequential()` initiates the model structure as a stack that has layers sequentially. <br >
  - `Sequential.add()`<sub>[5]</sub>: With sequential model, I can apply `add()` to add layers into `Sequential()` constructor. <br >
- `tensorflow.keras.layers.LSTM()`<sub>[6]</sub>: LSTM stands for Long Short-Term Memory which is a type of recurrent neural network that adds memory cells to keep long-term dependencies (long-term information).<br >
- `tensorflow.keras.layers.Dropout()`<sub>[7]</sub>: `Dropout` will set certain percent neurons to inactive (0) at this layer. This will prevent the model rely on specific neurons and avoid overfitting.<br >
- `tensorflow.keras.layers.Dense()`<sub>[8]</sub>: `Dense` creates a full-connected layer which every neuron in this layer is connected to all neurons in previous layer.<br >
- `tensorflow.keras.model.compile()`<sub>[9]</sub>: After the model is constructed, I call `compile()` to config loss function, optimizer, and metrics before training.<br >
  - Example: model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy']) <br >
  - loss means loss function which measure how wrong the model is during training. <br >
  - binary_crossentropy is a loss function to make prediction for two classes. (0 or 1, True or False) <br >
  - optimizer is used to decide how the model update weights during training. <br >
  - metrics=['accuracy] tell the model to evaluate accuracy metric during training. The accuracy metric shows how great the model prediction during training. <br >

## Reference:
[1] [train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)<br >
[2] [StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)<br >
[3] [iTex2Img](https://www.sciweavers.org/free-online-latex-equation-editor)<br >
[4] [tf.keras.Sequential](https://www.tensorflow.org/api_docs/python/tf/keras/Sequential)<br >
[5] [The Sequential model](https://www.tensorflow.org/guide/keras/sequential_model)<br >
[6] [Long short-term memory](https://en.wikipedia.org/wiki/Long_short-term_memory)<br >
[7] [tf.keras.layers.Dropout in TensorFlow](https://www.geeksforgeeks.org/deep-learning/tf-keras-layers-dropout-in-tensorflow/)<br >
[8] [Dense Layer (tf.keras.layers.Dense) in TensorFlow](https://www.geeksforgeeks.org/deep-learning/dense-layer-tf-keras-layers-dense-in-tensorflow/)
[9] [tf.keras.Model](https://www.tensorflow.org/api_docs/python/tf/keras/Model#example_2)




