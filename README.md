# Inventory-Monitoring-at-Distribution-centre
## Domain Overview
Distribution centers often use robots to move objects as a part of their operations. Objects are carried in bins which can contain multiple objects. In this project, you will have to build a model that can count the number of objects in each bin. A system like this can be used to track inventory and make sure that delivery consignments have the correct number of items.

## Problem Statement
Manual processes in traditional supply chain models may lead to low efficiency and waste of resources, such as employ time and machine cost.

## Solution Statement
In distribution centres, robots are often used to move objects as part of their operations. Bins size and the number of objects in each bin differs, thus delivery of correct consignments can be challenging. To complete the task efficiently, machine leaning could be utilized to predict the number of items in each bin. 
The machine learning model will be based on a pre-trained convolutional neural network, such as resnet 50. Then, it will be tuned on a few selected hyper parameters to improve model performance, for example, learning rate, batch size and number of epochs. Furthermore, model performance assessment will be based on a few selected metrics, that are suitable to this use case, such as cross entropy loss.

## Dataset and Inputs
The publicly available Amazon Bin Image Dataset will be used in this project. This dataset contains over 500,000 images, where each image contains one or more objects. In addition, the dataset contains JSM metadata from bins of a pod in an operating Amazon Fulfilment Centre, such as number of objects, it’s dimension and the type of object. Given the dataset, the task is to classify the number of objects in each bin.

![image info](./images/sample.jpg)

Example of an image from the dataset


## Project Design

The pipeline of the project is designed as the following steps:

1.	Download the data and upload to S3 bucket

2.	Complete multi-instance Hyperparameter tuning

3.	Model profiling and debugging

4.  Model Performance

6.	Endpoint deployment and Lambda quering

## Upload Data to S3
![image info](./images/s3.png)

## Multi-instance Hyper Parameter Tuning

Parameters and range seleted:

1. "learning_rate": (0.001, 0.1)

2. "batch_size": [32, 64, 128, 256, 512]


### Training Job Completed
![image info](./images/training.png)

### Check Best Hyper Parameters

![image info](./images/result.png)


## Model Profiling and Degugging

### Training Job with Debugger Completed
![image info](./images/debugger.png)

## Model Performance
![image info](./images/performance.png)

Model performance shows a steady decrease of both training and validation cross entropy loss
## Model Deploying and Querying

### Endpoint Deployed
![image info](./images/endpoint.png)

### Lambda Test Result
![image info](./images/lambda_test.png)

### All 3 sample images are predicted successfully
![image info](./images/response1.png)

![image info](./images/response2.png)

![image info](./images/response3.png)
