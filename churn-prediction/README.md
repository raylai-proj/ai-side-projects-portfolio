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


