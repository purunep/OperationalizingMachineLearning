
# Operationalizing Machine Learning
This project is part of the Udacity Azure ML Nanodegree. In this project, We have built and deploy model and consume the endpoint using REST API call. For building, deploying the model We are using Microsoft Azure Auto ML and also using the Azure ML pipeline. For the training we are using Bank marketing training data set from the following [link](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv/)
The classfication model goal is to predicts if a client will subscribe to a fixed term deposit with a financial institution. 

## Architectural Diagram
Here is the Architectural diagram that shows all the main step from creating a dataset to Auto ML and choosing the best model from the trained model. After we choose the best model, we published and consume the endpoint.
![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/ArchitectureDiagram.png)


## Key Steps
#### Register the DataSet
we registered the dataset from web url:  https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv 
and once registered it will show as below:
#### Create a AutoML experiment
After we registered the dataset create the AutoML experiment by selecting the dataset. Which will take around 30-40 minutes to complete.
#### View and Select the best model
Once AutoML completed view the best model and select it to see more detail metrics about it
#### Deploy the best model
#### Enable Application insights to the best model
We enable application insights with the following code from logs.py file
#### View the model endpoint in Swagger
#### Consume the deployed model
Consume the deployed model using endpoint.py. We are doing the POST call here with JSOn payload.
#### Apache benchmark
#### Using SDK to create the pipeline
We also used the Jupyter Notebook to create a pipeline endpoints. Here are different steps for it

## Further Improvement
We can further improve the model by cleaning data so that the datas is balanced and not biased to any one. Also we can run AutoML for longer duration to try out different models.
## Screen Recording
Here is the screencast that demonstrated all the above mentioned process: 

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
