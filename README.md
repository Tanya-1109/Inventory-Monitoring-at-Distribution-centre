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



## Project Design

The pipeline of the project is designed as the following steps:

1.	Download the data and upload to S3 bucket

2.	Complete multi-instance Hyperparameter tuning

3.	Model profiling and debugging

4.  Model Performance

6.	Endpoint deployment and Lambda quering

## Upload Data to S3

![s3](https://user-images.githubusercontent.com/107848751/233067804-1ce0310e-5cf9-4241-8734-284bbc35e37d.png)

## Multi-instance Hyper Parameter Tuning

Parameters and range seleted:

1. "learning_rate": (0.001, 0.1)

2. "batch_size": [32, 64, 128, 256, 512]


### Training Job Completed

![training](https://user-images.githubusercontent.com/107848751/233067981-2bf60c7c-dca4-45b6-8241-89850dbd1ca0.png)


### Check Best Hyper Parameters


![result](https://user-images.githubusercontent.com/107848751/233068087-7348b455-74a9-4577-b7c9-029ebb87f636.png)


## Model Profiling and Degugging

### Training Job with Debugger Completed

![debugger](https://user-images.githubusercontent.com/107848751/233068146-aec65b27-103a-4ff0-acd8-f1114534e89d.png)

## Model Performance

![performance](https://user-images.githubusercontent.com/107848751/233068201-800ae100-8841-4d0d-a124-37df1673441a.png)

Model performance shows a steady decrease of both training and validation cross entropy loss
## Model Deploying and Querying

### Endpoint Deployed
![endpoint](https://user-images.githubusercontent.com/107848751/233068283-3b6fa825-5341-4461-a1aa-eaac01816d0d.png)


### Lambda Test Result
![lambda_test](https://user-images.githubusercontent.com/107848751/233068426-2a393760-ac78-4548-aca8-4571c44ed2f5.png)


### All 3 sample images are predicted successfully

![response1](https://user-images.githubusercontent.com/107848751/233068523-4bd48c7f-c677-43ed-9eca-8ddc72568dee.png)

![response2](https://user-images.githubusercontent.com/107848751/233068548-ba2fec25-431a-4815-8fc4-2e7ac2b400d0.png)

![response3](https://user-images.githubusercontent.com/107848751/233068617-5e9cb09a-6873-4c2c-897c-6d8d70c1d90d.png)

