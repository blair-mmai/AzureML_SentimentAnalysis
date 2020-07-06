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



* You will see this blank architecture on the screen guiding you in how to set up your experiment architecture:

Now it is time to start adding the modules to your experiment canvas.

### **Step 3b – Load Your Data**

* Locate your dataset in My Datasets on the left-hand menu under My Datasets
* Drag & Drop the Dataset to the right-hand side where your architecture canvas is



**Other reference material:**
(1) for more information on setting up your workspace, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/create-workspace
(2) For another tutorial example, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/tutorial-part1-credit-risk
