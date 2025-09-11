# Customer Churn Prediction <br >
## Machine Learning Recap: <br >
- Feature : Feature means measurable properties in training datasets. For example, in house rent prediction in apartment, features can include square footage, number of bedrooms and bathrooms, year built, and location. <br >
- Numerical Vector Representation : Numerical vector representation is a numeric form (a ordered number list) of data after embedding the original data. Machine learning models only accepts numeric data, so transforming non-numeric data into numeric vector representation is part of data preprocessing before training models using those data. <br >
- Embedding : Embedding means transform original data to numerical vector representation. <br >
- one-hot encoding : One-hot encoding means gives each categorical label one vector class to represent it's category. e.g. to represent cat, dog, bird, <br >
  - cat = [1, 0, 0], dog = [0, 1, 0], bird = [0, 0, 1] <br >
- __X__ , __y__ : __X__ means training dataset = input = feature. __y__ means test dataset = output = label. <br >
- epochs : Epochs means how many time the full training dataset pass through the model. For example, epochs = 50 means the model will train with that dataset 50 times. <br >
- batch_size : Batch size means how many samples the model will process at once. For example, batch_size = 128 means the model will process 128 samples at a time in the full training dataset, then update weights. <br >
- evaluate : Evaluate means after model trains with training dataset, we feed the model test dataset (dataset the model didn't see before) for prediction and measure how good the trained moded is. <br >
- history : History is a log object contains training metric (loss, accuracy) for each epoch and validation metric. When I train a model with training dataset, it returns a history object which I can draw learning curve, e.g. loss vs. epochs, accuracy vs. epochs. <br >
