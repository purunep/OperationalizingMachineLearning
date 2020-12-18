
# Operationalizing Machine Learning
This project is part of the Udacity Azure ML Nanodegree. In this project, We have built and deploy model and consume the endpoint using REST API call. For building, deploying the model We are using Microsoft Azure Auto ML and also using the Azure ML pipeline. For the training we are using Bank marketing training data set from the following [link](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv/)
The classfication model goal is to predicts if a client will subscribe to a fixed term deposit with a financial institution. 

## Architectural Diagram
Here is the Architectural diagram that shows all the main step from creating a dataset to Auto ML and choosing the best model from the trained model. After we choose the best model, we published and consume the endpoint.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/ArchitectureDiagram.png)


## Key Steps
#### Register the DataSet
we registered the dataset from web url [link](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv/)
and once registered it will show as below:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/dataset.png)

#### Create a AutoML experiment
After we registered the dataset create the AutoML experiment by selecting the dataset. We choosed the target column as "y" as shown below.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/experiment.png)

We defined the exit criteria as shown below and ran the experiment for 1 hour.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/exitcriteria.png)

The compute target we created is shown below:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/compute.png)

#### View and Select the best model
Once AutoML run completed, view the best model and select it to see more detail metrics about it.
Here is the screen that shows Auto ML run completed:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/run_completed2.png)

Here are all the models that run during Auto ML training.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/allmodels.png)

We found "VotingEnsemble" as the best model, with accuracy of 0.91897.
We can view the metrics details by selecting it as shown below:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/metrics_updated.png)


#### Deploy the best model
Select the best model and deploy the model as shown below:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/deploymodel_auth.png)

### Enable Application insights
Application insights is a analytics tools to help us diagnose issues and to monitoring all of the service.
We can enable application insights by running the python script "logs.py" as shown below

#### Code to enable Application insights

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/enable_app_insights_code.png)

It shows as below after we ran

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/ranlogpy.png)

Once Application insights enabled we can check in UI and also see the page as below:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/application_insights_true.png)


![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/application_insights_page.png)

#### View the model endpoint in Swagger
Using Swagger, we can see all available endpoints and sample to call each endpoint. Here is the Swagger UI, generated for the deployed Auto ML model.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/swagger3.png)


![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/swagger_ui1.png)

#### Consume the deployed model
Consume the deployed model using endpoint.py, We have updated the endpoint.py for specifying the deployed model score url and the key as shown below:


![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/endpointupdated.png)

 We are doing the POST call here with JSON payload. Then ran the script as shown in command below: 
 
![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/endpointcall.png)

#### Apache Benchmark
Also, I have created teh benmark using Apache Benchmark command. The screen below shows the ran benchmark metrics:

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/ab1.png)


![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/ab_run.png)


#### Using SDK to create the pipeline
We also used the Jupyter Notebook to create a pipeline endpoints. we have updated the different parameters in the notebook and
ran each steps from the notebook "aml-pipelines-with-automated-machine-learning-step.ipynb". The outputs of each step are shown in the
[Notebook](https://github.com/purunep/udacityProject2/blob/main/starter_files/aml-pipelines-with-automated-machine-learning-step.ipynb)

The follwing screen shows the run details widget :
![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/rundetails.png)

The screen below shows the ran pipeline and in completed status.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/pipeline_run_completed.png)


![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/pipline_completed2.png)


The pipeline is then submitted and deployed. It has also the endpoints that we can call using SDK.

![alt text](https://github.com/purunep/udacityProject2/blob/main/Images/pipeline_endpoint.png)


## Further Improvement
We can further improve the model by cleaning data so that the datas is balanced and not biased to any one. Also we can run AutoML for longer duration to try out different models.

## Screen Recording
Here is the screencast that demonstrated all the above mentioned process. Plese click on 
[link](https://www.youtube.com/watch?v=wGTl6yhKCxo&feature=youtu.be)

