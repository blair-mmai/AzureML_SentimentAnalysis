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

Before starting this tutorial, you will need to:
1. Download [Bathurst_Tutorial_sentiment.csv](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis) 
> To download the file from the link, click on Code and select Download Zip
> Unzip the file and keep note of where you have it as you will need it's location later in the tutorial

![download file](https://user-images.githubusercontent.com/55206834/86694747-e6403f00-bfd9-11ea-9069-397e50b29005.png)

2. Ensure you have Microsoft Azure access – you should have this from MMAI 863.  Try your login [here](https://studio.azureml.net/)  

If you do not have an Azure account, please go here for steps to create your account (link to how to set up your account pending)

## **Actions**

Now that you have Azure access and the file you want to use downloaded; we are ready to begin the tutorial.

### **Step 1 – Select your workspace** (1)
* Navigate to [https://studio.azureml.net/](https://studio.azureml.net/) and log on to Azure studio 
* Once logged in, select your workspace from the top right-hand menu

![Select Workspace](https://user-images.githubusercontent.com/55206834/86695692-c52c1e00-bfda-11ea-965b-75de8e32ee21.png)

You should now be at this screen:

![Main Screen](https://user-images.githubusercontent.com/55206834/86852829-6e2e5380-c083-11ea-832b-2115a97f0099.png)

### **Step 2 – Load your Dataset** (2)

* Click on _DATASETS_ in the left-hand column
* Click the _+NEW_ in the bottom left of the workspace window

![New Dataset](https://user-images.githubusercontent.com/55206834/86853621-d92c5a00-c084-11ea-9575-5dd06fa43001.png)

* In the left-hand navigation bar with the grey menu, select _DATASET_ 

![Dataset](https://user-images.githubusercontent.com/55206834/86649527-d7449700-bfaf-11ea-80a6-d768a5475156.png)

* Select _FROM LOCAL FILE_

![From local file](https://user-images.githubusercontent.com/55206834/86853879-62439100-c085-11ea-8313-69a1d560f5f8.png)

* Navigate to the _Bathurst_Tutorial_sentiment.csv_ file you downloaded in the pre-conditions
* Click the _checkmark_

![checkmark](https://user-images.githubusercontent.com/55206834/86716140-e860c880-bfee-11ea-9d84-2fd4b647e0d5.png)

* You now have your dataset loaded and ready to use

Your screen should now look like this:

![Final screen - Step 2](https://user-images.githubusercontent.com/55206834/86649703-fcd1a080-bfaf-11ea-9375-87f612ae98f5.png)

### **Step 3 – Setup your Sentiment Analysis Architecture**

We are now ready to set up our Architecture. At the end of the tutorial, your Architecture should look like this:

![Architecture](https://user-images.githubusercontent.com/55206834/86651775-d01e8880-bfb1-11ea-85cb-810bc285cf18.png)

### **Step 3a – Create an Experiment**

* Click _EXPERIMENTS_
* Click the _+NEW_ in the bottom left of the workspace window

![New](https://user-images.githubusercontent.com/55206834/86652133-21c71300-bfb2-11ea-8685-e0b2c743a750.png)

* At this point, you can either choose a Blank Experiment or Experiment template (if you want to start from an existing template)
* For the purposes of this tutorial, click _Blank Experiment_

![Blank Experiment](https://user-images.githubusercontent.com/55206834/86652060-11169d00-bfb2-11ea-96ab-632889a31b28.png)

* You will see this blank architecture on the screen guiding you in how to set up your experiment architecture:

![blank architecture](https://user-images.githubusercontent.com/55206834/86652022-0825cb80-bfb2-11ea-8484-dcef42316fbf.png)

Now it is time to start adding the modules to your experiment canvas.

### **Step 3b – Load Your Data**

* Click on _Saved Datasets_
* Click on _My Datasets_
* Locate your dataset in My Datasets on the left-hand menu under My Datasets
* Drag & Drop the Dataset to the right-hand side where your architecture canvas is

![Drag and Drop](https://user-images.githubusercontent.com/55206834/86700724-58675280-bfdf-11ea-912c-e499ab376e0f.png)

### **Step 3c – Pre-process your data** (3)

* In the search box _Search Experiment Items_ type in “_preprocess_”, 

![search](https://user-images.githubusercontent.com/55206834/86696966-f22d0080-bfdb-11ea-9878-e152865914d6.png)

* You will see _Preprocess Text_ Module under Text Analytics

![Preprocess](https://user-images.githubusercontent.com/55206834/86702468-fe678c80-bfe0-11ea-80e4-da39f9e663fc.png)

* Drag and Drop _Preprocess Text_ to your canvas **below** your dataset box
* **Connect** the dataset to Preprocess Text module (left connector)

![Connect](https://user-images.githubusercontent.com/55206834/86653572-4a9bd800-bfb3-11ea-86a8-8e48f9833291.png)

* Set properties:
* > click on the _Preprocess Text_ module, and look at the right-hand column
* > Here you will see all the available pre-processing options to select from
* > Select the type of preprocessing you would like to do from the right-hand side of the screen
* > For the purposes of this tutorial, we accepted all the **default cleaning** as shown below:

![Properties](https://user-images.githubusercontent.com/55206834/86653645-57203080-bfb3-11ea-8d8e-c1c8e8777488.png)

* > Click _Launch Column selector_

![launch column selector](https://user-images.githubusercontent.com/55206834/86697725-a7f84f00-bfdc-11ea-8efc-c5101ada4a56.png)

* > Click _By Name_ on the left-hand side
* > Select only the _Sentence_ field and move it to the right-hand side under _SELECTED COLUMNS_ using the arrow in the center indicating you want to be pre-processed 

![sentence pre click](https://user-images.githubusercontent.com/55206834/86699391-22759e80-bfde-11ea-858f-2a8654204a1c.png)

Note: all other fields should be on the left-hand side under _AVAILABLE COLUMNS_
* Click on the _checkmark_

![sentence](https://user-images.githubusercontent.com/55206834/86699781-85673580-bfde-11ea-9882-61bc3aec6390.png)

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
* Click on _BY NAME_ on the left-hand side
* Select _Preprocessed Sentence_ and move it to the right-hand side under _SELECTED COLUMNS_ using the arrow in the center 
Note: all other fields should be on the left-hand side under _AVAILABLE COLUMNS_
* Click on the _checkmark_

![select preprocessed sentence](https://user-images.githubusercontent.com/55206834/86701858-65387600-bfe0-11ea-833c-886b436e4b45.png)

* Set the properties you want to use to vectorize the data
* For the purposes of this tutorial, we have used hashing **bitsize** of _8_  with **n-grams** of _1_

![properties hash](https://user-images.githubusercontent.com/55206834/86655770-f98ce380-bfb4-11ea-9dde-c3a7905bea03.png)

* _Run_ the module by right-clicking on it and selecting Run (remember to look for the green checkmark  on your module indicating a successful run before moving on)

### **Step 3e – Select the data to pass to your model**

After running the feature hashing modules, we now have clean data with new vectorized features. We need to select those features and the target features to pass to our ML algorithm.

There is a _Select Columns in Dataset_ module available to assist us with this.
* In the search box, enter “_select_”, and you see _Select Columns in Dataset_ Module under Data Transformation

![search select cols](https://user-images.githubusercontent.com/55206834/86702938-6b7b2200-bfe1-11ea-86d9-958fa04f4925.png)

* Drag and Drop _Select Columns in Dataset_ to your canvas
* Connect the _Feature Hashing_ module to _Select Columns in Dataset_

![connect](https://user-images.githubusercontent.com/55206834/86656720-ac5d4180-bfb5-11ea-8b21-2ea50e85c0d3.png)

* Set properties by clicking on the module, and then clicking on _Launch column selector_
* Select the required columns for ML to use (In our case study, we **exclude** the columns “_Sentence_” and “_Preprocessed Sentence_”)
* > Click on WITH RULES on the left-hand side
* > Select **Beginning with all columns** and **Exclude** the **column names** _Sentence_ and _preprocessed sentence_) *remember your ML algorithm doesn’t understand plain text so it only wants the vectorized data
* > Click on the _checkmark_

![begin with all cols](https://user-images.githubusercontent.com/55206834/86704054-81d5ad80-bfe2-11ea-8c85-1c3970abaaf8.png)

You should now see this above _Launch column selector_:

![hash select cols](https://user-images.githubusercontent.com/55206834/86705854-4936d380-bfe4-11ea-996a-7ad9170a6d5b.png)

* _Run_ the module by right-clicking on it and selecting _Run selected_ (remember to look for the green checkmark of a successful run before moving on)

### **Step 3f – Split your data into training and testing data** (5)

We will use Azure’s built-in Split Data module.
* In the search box, enter “_split_”, and you see _Split Data_ Module under _Data Transformation_

![split](https://user-images.githubusercontent.com/55206834/86708145-a3d12f00-bfe6-11ea-900f-09501b887606.png)

* Drag and Drop _Split Data_
* **Connect** the _Select Columns_ in Dataset module to _Split Data_

![connect](https://user-images.githubusercontent.com/55206834/86659784-2098e480-bfb8-11ea-8ccd-22babc8020bc.png)

* Set properties by clicking on the module
* Select a single column for the stratification. In our instance: _Polarity_
* > Click on _Launch column selector_
* > Click on _BY NAME_
* > Click on _Polarity_ in the left-hand column and move it to the right-hand column under _SELECTED COLUMNS_ using the arrow in the middle

![stratified split](https://user-images.githubusercontent.com/55206834/86706426-ded26300-bfe4-11ea-8613-9b271b886100.png)

* > Click on the _checkmark_

* Set the remaining properties for your data split
* > In our example we split the data into _80% training_ data and _20% testing_ data by setting the _Fraction of rows in the firs..._ to 0.8
* > _Check the box_ for _Randomized split_
* > Set your _Random seed_ = 42 so that your results are reproduceable
* > Set _Stratified split_ to _True_

![split properties](https://user-images.githubusercontent.com/55206834/86707403-e9d9c300-bfe5-11ea-909d-dac14bc8cde8.png)

* _Run_ the module by right-clicking and selecting _Run selected_

We now have our dataset ready for training. Let us begin!

### **Step 3g – Select and train your model** (6)

* Instantiate the model by selecting the classification algorithm.
* In the search box, enter “_classification_”, and you see the classification algorithms available
* Choose your algorithm. In our tutorial, we will be using _Two-class Boosted Decision Tree_
* Drag and Drop the _Two-class Boosted Decision Tree_ classifier to your canvas

![search DT](https://user-images.githubusercontent.com/55206834/86709223-b9932400-bfe7-11ea-9db9-47eff1892798.png)

* In the search box, enter “_Train_” to select the _Train Model_ module
* Drag and Drop the _train model_ module to your canvas

![train](https://user-images.githubusercontent.com/55206834/86709318-d29bd500-bfe7-11ea-9f91-8bb53f1a3936.png)

* Connect _Two-class Boosted Decision Tree_ to the left input node of _Train Model_
* Connect the _Training Dataset_ (left output node of _Split Data_ module) to the right input node of **Train Model**

![Connect](https://user-images.githubusercontent.com/55206834/86660409-b59bdd80-bfb8-11ea-97bd-da2b99f031b4.png)

* Set properties by clicking on the module _Train Model_ 
* Click on _Launch Column Selector_ 
* > Click on _BY NAME_
* > Select the _Polarity_ column on the right-hand side and move it to the left-hand side under _SELECTED COLUMNS_ using the arrow in the middle
* > Click on the _checkmark_

![select cols](https://user-images.githubusercontent.com/55206834/86710734-47bbda00-bfe9-11ea-98ef-7aa6a6e078e9.png)

* Set the _properties_ for your model.
* In our tutorial, we used:
* > Max number of leaves = 20
* > Min number of samples = 10
* > Learning rate = 0.2
* > Number of trees constructed = 100
* > Random number seed = 42

![DT properties](https://user-images.githubusercontent.com/55206834/86710052-8dc46e00-bfe8-11ea-9c6f-471bb6e004e3.png)

* _Run_ the _Train Model _module by right-clicking on it and selecting _Run Selected_

The model training is now complete. 

### **Step 3h – Evaluate your model’s performance**

* In the search box, enter “_score_”, and you see _Score Model_ module
* Drag and Drop the _Score Model_ to your canvas

![score](https://user-images.githubusercontent.com/55206834/86711582-168fd980-bfea-11ea-91e4-861c20920edf.png)

* In the search box, enter “_Evaluate_”, and you see _Evaluate Model_ module
* Drag and Drop the _Evaluate Model_ to your canvas

![evaluate](https://user-images.githubusercontent.com/55206834/86711510-02e47300-bfea-11ea-9669-8f975b7f620d.png)

* Connect the output node of _Train Model_ to the left input node of _Score Model_
* Connect _Data Split_ (right output node) to the right input node of _Score Model_
* Connect _Score Model_ to _Evaluate Model_

![connect](https://user-images.githubusercontent.com/55206834/86661600-df093900-bfb9-11ea-815a-90d1a2711b88.png)

* _Run_ the _Evaluate Model_ module by right-clicking and selecting _Run selected_
* You can visualize the results by right-clicking on _evaluate model_ and selecting _Evaluation Results_ -> _Visualize_

![visualize](https://user-images.githubusercontent.com/55206834/86662039-5343dc80-bfba-11ea-987b-0c68082056d4.png)

## **Analyze results**

You can now compare the results you achieved in this tutorial to the results of your NLP Individual Assignment.  
Feel free to play around with the tutorial and change your data pre-processing or the model you used or it’s parameters.
Team Bathurst found we achieved similar results to the NLP IND assignment question #2 using this tutorial in far less time than it took to build our code submission. 

## **Deploying your model**

When you are satisfied with your model, it is time to deploy it to production.  

## **Step 1 - Convert the training experiment to a Predictive experiment**

* Click _SET UP WEB SERVICE_ and then _Predictive web service (recommended)_

![setup web service](https://user-images.githubusercontent.com/55206834/86718092-c49e8200-bff0-11ea-8288-ff89d6e6c835.png)

![warning](https://user-images.githubusercontent.com/55206834/86663588-df0a3880-bfbb-11ea-9353-07aaba61152f.png) At this point, if you don’t see the _SET UP WEB SERVICE_ option, you may not have run your full experiment, please go back and do so now and try again.

You will now see a second tab with your Predictive experiment.

![pred exp](https://user-images.githubusercontent.com/55206834/86663301-95b9e900-bfbb-11ea-978e-68a16abfa287.png)

* Select _RUN_ from the bottom menu to run the full model

![run](https://user-images.githubusercontent.com/55206834/86719837-712d3380-bff2-11ea-8ed1-2e790445bb43.png)

* Right-click on the _Score Model_ module and select _Scored Dataset_ and then _Visualize_ to ensure it has all the vectorized data (similar to the experiment data view)

![scored dataset](https://user-images.githubusercontent.com/55206834/86720831-66bf6980-bff3-11ea-9fd5-34716405a02c.png)

* The Score Model will contain all the features used to train the model plus 2 other features (Scored Labels, and Scored Probabilities) 
* In the search in the left-hand column, type "select columns"

![select cols](https://user-images.githubusercontent.com/55206834/86721265-cfa6e180-bff3-11ea-90af-920a51a1f900.png)

* Drag and Drop _Select Columns in Dataset_ to the canvas placing it between the _Score Model_ and _Web service output_ 
* Reconnect the _Score Model_ output node to the _Select Columns in Dataset_ input node
* Connect the _Select Columns in Dataset_ output node to the _Web service output_ top (input) node
* Click on _Select Columns in Dataset_ module
* Click on _Launch column selector_ 
* Click on BY NAME on the right-hand side
* Scroll all the way down to find **Scored Labels** and **Scored Probabilities** in the Available columns and select them both (click first, hold down shift and click the second)
* Move them to the right hand Selected columns column by clicking the arrow in the middle
* Click on the _checkmark_

![score labels](https://user-images.githubusercontent.com/55206834/86723026-848dce00-bff5-11ea-9234-f3e25e8bf8d5.png)

* _Run_ again the Predictive experiment by selecting _Run_ from the bottom menu to get the following: 

The Web service can now be deployed 

## **Step 2 - Deploy**

* Click _DEPLOY WEB SERVICE_ 

![deploy](https://user-images.githubusercontent.com/55206834/86723390-d9c9df80-bff5-11ea-948b-07fbf382ce85.png)

* Click _Deploy_ 

![deploy 2](https://user-images.githubusercontent.com/55206834/86663217-7e7afb80-bfbb-11ea-9a09-399d04fce5cf.png)

## **Step 3 – Test**

* You can test your newly created web service by selecting Test Web Service

![test](https://user-images.githubusercontent.com/55206834/86663701-fe08ca80-bfbb-11ea-9953-736daa295c5a.png)

You will see a screen to test your web service.  Type in a sentence and see your prediction. 

![test 2](https://user-images.githubusercontent.com/55206834/86663780-11b43100-bfbc-11ea-90fb-b1dfd906de35.png)

# **Conclusion**

We started this exercise with a business problem to solve.  
As a member of the Data Science team at Bathurst Inc., you have been tasked to create a sentiment analysis tool using Microsoft Azure ML Studio to predict whether tweets related to your products and services are positive and negative for the purposes of:

* Providing the customer experience team with “strong positive” tweets so they can generate an outbound marketing campaign to get promoters to provide online recommendations and strengthen your online presence
* Providing the customer retention team with “strong negative” tweets so they can address the issues with the customers and turn detractors into (at worst) neutral, (at best) promoters of the company

Now that you have a sentiment analysis experiment, you can easily extend it for use as an API in a custom-built script for free (for up to 1,000 transactions) to test if this is valuable by:
* Scraping tweets and classifying them as positive or negative
* Generating some reports on that data for your customer experience team

**Other reference material:**
(1) for more information on setting up your workspace, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/create-workspace
(2) For another tutorial example, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/tutorial-part1-credit-risk
(3) To learn more about preprocessing data in Azure ML studio, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/preprocess-text?redirectedfrom=MSDN
(4) To learn more about the hashing function, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/feature-hashing?redirectedfrom=MSDN
(5) To learn more about how to split data in Azure ML, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/split-data?redirectedfrom=MSDN
(6) To learn more about training models, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/train-model?redirectedfrom=MSDN
(7) For more information on web services, please refer to:https://services.azureml.net/subscriptions/9887b0c8-8f21-4ab3-9265-d4e879c54888/resourceGroups/bamservice/providers/Microsoft.MachineLearning/webServices/Sentiment2create.2020.7.3.22.56.47.8/test/rrs


