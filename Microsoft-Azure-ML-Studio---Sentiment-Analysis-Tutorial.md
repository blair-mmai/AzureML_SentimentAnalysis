# **Scenario-Based Tutorial**

## **Scenario**
As a member of the Data Science team at Bathurst Inc., you have been tasked to create a sentiment analysis tool using Microsoft Azure ML Studio to predict whether tweets related to your products and services are positive and negative for the purposes of:

* Providing the customer experience team with “strong positive” tweets so they can generate an outbound marketing campaign to get promoters to provide online recommendations and strengthen your online presence
* Providing the customer retention team with “strong negative” tweets so they can address the issues with the customers and turn detractors into (at worst) neutral, (at best) promoters of the company

## **Task Outline**

In this tutorial you will:
* Learn how to setup a Microsoft Azure ML Studio experiment
* Create an architecture for doing sentiment analysis
* Learn how to configure your Azure ML architecture
* Use tutorial_sentiment_train.csv (a combined version of sentiment_train.csv and sentiment_test.csv from your NLP IND assignment) to see how the Azure ML algorithm performs relative to other exercises you have already done.
* Learn how to deploy an Azure ML Sentiment Analysis algorithm into production

## **Pre-Conditions**

Before starting this tutorial, you will need:
1. Download [Bathurst_Tutorial_sentiment.csv](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis) 
2. Microsoft Azure access – you should have this from MMAI 863.  Try your login [here](https://studio.azureml.net/).  

If you do not have an Azure account, please go here for steps to create your account (link to how to set up your account pending)

## **Actions**

Now that you have Azure access and the file you want to use downloaded; we are ready to begin the tutorial.

### **Step 1 – Select your workspace** (1)
* Navigate to [https://studio.azureml.net/](https://studio.azureml.net/) and log on to Azure studio 
* Once logged in, select your workspace from the top right-hand menu

![Select Workspace](https://user-images.githubusercontent.com/55206834/86645925-d3634580-bfac-11ea-8d43-255b5d41f7ce.png)

You should now be at this screen:

![Workspace View](https://user-images.githubusercontent.com/55206834/86646031-e7a74280-bfac-11ea-9b6d-1d40106c95af.png)

### **Step 2 – Load your Dataset** (2)

* Click the _+NEW_ in the bottom left of the workspace window

![New](https://user-images.githubusercontent.com/55206834/86649646-f0e5de80-bfaf-11ea-8ed6-0a8636ed4353.png)

* Select _DATASET_

![Dataset](https://user-images.githubusercontent.com/55206834/86649527-d7449700-bfaf-11ea-80a6-d768a5475156.png)

* Select _FROM LOCAL FILE_

![From local file](https://user-images.githubusercontent.com/55206834/86649592-e62b4980-bfaf-11ea-80be-0f3bde1a6add.png)

* Navigate to the _Bathurst_Tutorial_sentiment.csv_ file you downloaded in the pre-conditions
* Click the _checkbox_

![checkbox](https://user-images.githubusercontent.com/55206834/86649478-cb58d500-bfaf-11ea-8042-90d48261a91d.png)

* You now have your dataset loaded and ready to use

Your screen should now look like this:

![Final screen - Step 2](https://user-images.githubusercontent.com/55206834/86649703-fcd1a080-bfaf-11ea-9375-87f612ae98f5.png)

### **Step 3 – Setup your Sentiment Analysis Architecture**

We are now ready to set up our Architecture. At the end of the tutorial, your Architecture should look like this:

![Architecture](https://user-images.githubusercontent.com/55206834/86651775-d01e8880-bfb1-11ea-85cb-810bc285cf18.png)

### **Step 3a – Create an Experiment**

* Click _EXPERIMENT_
* Click the _+NEW_ in the bottom left of the workspace window

![New](https://user-images.githubusercontent.com/55206834/86652133-21c71300-bfb2-11ea-8685-e0b2c743a750.png)

* At this point, you can either choose a Blank Experiment or Experiment template (if you want to start from an existing template)
* For the purposes of this tutorial, click _Blank Experiment_

![Blank Experiment](https://user-images.githubusercontent.com/55206834/86652060-11169d00-bfb2-11ea-96ab-632889a31b28.png)

* You will see this blank architecture on the screen guiding you in how to set up your experiment architecture:

![blank architecture](https://user-images.githubusercontent.com/55206834/86652022-0825cb80-bfb2-11ea-8484-dcef42316fbf.png)

Now it is time to start adding the modules to your experiment canvas.

### **Step 3b – Load Your Data**

* Locate your dataset in My Datasets on the left-hand menu under My Datasets
* Drag & Drop the Dataset to the right-hand side where your architecture canvas is

![Drag and Drop](https://user-images.githubusercontent.com/55206834/86652096-196ed800-bfb2-11ea-8b02-297c7269c1c8.png)

### **Step 3c – Pre-process your data** (3)

* In the search box, enter “_preprocess_”, and you see _Preprocess Text_ Module under Text Analytics

![Preprocess](https://user-images.githubusercontent.com/55206834/86653366-217b4780-bfb3-11ea-9a86-cf4c50eb4f07.png)

* Drag and Drop _Preprocess Text_ to your canvas
* **Connect** the dataset to Preprocess Text module (left connector)

![Connect](https://user-images.githubusercontent.com/55206834/86653572-4a9bd800-bfb3-11ea-86a8-8e48f9833291.png)

* Set properties:
* > click on the _Preprocess Text_ module, and then _Launch column selector_ from the right-hand column
* > Here you will see all the available pre-processing options to select from
* > Select the type of preprocessing you would like to do from the right-hand side of the screen
* > For the purposes of this tutorial, we accepted all the **default cleaning** as shown below:

![Properties](https://user-images.githubusercontent.com/55206834/86653645-57203080-bfb3-11ea-8d8e-c1c8e8777488.png)

* > Click _Launch Column selector_
* > Select the _Sentence_ field to be pre-processed

![Sentence](https://user-images.githubusercontent.com/55206834/86654338-df9ed100-bfb3-11ea-9179-f4d6c59f519f.png)

* Run the module by right-clicking on the module and selecting _Run Selected_ from the menu 
* You will know it completed properly by the green checkmark that shows up

![Run Success](https://user-images.githubusercontent.com/55206834/86654388-e9283900-bfb3-11ea-89f3-34c8a1bb2797.png)


### **Step 3d – Vectorization**

The next step is to extract features you want to use using feature hashing.

* In the search box, enter “_feature_”, and you see _Feature Hashing_ Module under Text Analytics

![hashing](https://user-images.githubusercontent.com/55206834/86654927-55a33800-bfb4-11ea-8cf6-21d40f5edb2d.png)

* Drag and Drop _Feature Hashing_
* Connect the output of the Preprocess Text module to the input of the Feature Hashing module

![hashing success](https://user-images.githubusercontent.com/55206834/86654885-4e7c2a00-bfb4-11ea-8fe7-743fc216ec5c.png)

* _Launch column selector_ to select the features you want to include
* For the purposes of this tutorial, Select _BEGIN WITH NO COLUMNS_ and select _Preprocessed Sentence_ 

![begin with no columns](https://user-images.githubusercontent.com/55206834/86656100-36f17100-bfb5-11ea-9194-15519e89fd57.png)

* Set the properties you want to use to vectorize the data
* For the purposes of this tutorial, we have used hashing **bitsize** of _8_  with **n-grams** of _1_

![properties hash](https://user-images.githubusercontent.com/55206834/86655770-f98ce380-bfb4-11ea-9dde-c3a7905bea03.png)

* Run the module by right-clicking on it and selecting Run (remember to look for the green checkmark of a successful run before moving on)

### **Step 3e – Select the data to pass to your model**

After running the feature hashing modules, we now have clean data with new vectorized features. We need to select those features and the target features to pass to our ML algorithm.

There is a _Select Columns in Dataset_ module available to assist us with this.
* In the search box, enter “_select_”, and you see _Select Columns in Dataset_ Module under Data Transformation

![search select cols](https://user-images.githubusercontent.com/55206834/86657043-eb8b9280-bfb5-11ea-9b0b-ca652e13a881.png)

* Drag and Drop _Select Columns in Dataset_ to your canvas
* Connect the _Feature Hashing_ module to * Select Columns in Dataset

![connect](https://user-images.githubusercontent.com/55206834/86656720-ac5d4180-bfb5-11ea-8b21-2ea50e85c0d3.png)

* Set properties by clicking on the module, and then clicking on _Launch column selector_



**Other reference material:**
(1) for more information on setting up your workspace, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/create-workspace
(2) For another tutorial example, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/tutorial-part1-credit-risk
(3) To learn more about preprocessing data in Azure ML studio, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/preprocess-text?redirectedfrom=MSDN
(4) To learn more about the hashing function, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/feature-hashing?redirectedfrom=MSDN
