# **Scenario-Based Tutorial**

For a description of the Business Problem you are solving in this tutorial, please refer to the [Overview](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis/wiki/Overview-of-Microsoft-Azure-ML-Studio-for-Sentiment-Analysis) page.

## **Task Outline**

In this tutorial you will:
* Learn how to set up a Microsoft Azure ML Studio experiment
* Create an architecture for doing sentiment analysis
* Learn how to configure your Azure ML architecture
* Use tutorial_sentiment_train.csv (a combined version of sentiment_train.csv and sentiment_test.csv from your NLP IND assignment) to see how the Azure ML algorithm performs relative to other exercises you have already done using this dataset.
* Learn how to deploy an Azure ML Sentiment Analysis algorithm into production

## **Pre-Conditions**

Before starting this tutorial, you will need to:
1. Download [Bathurst_Tutorial_sentiment.csv](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis) 
> To download the file from the link, click on Code and select Download Zip
> Unzip the file and keep a note of where you have it as you will need it's location later in the tutorial

![download file](https://user-images.githubusercontent.com/55206834/86694747-e6403f00-bfd9-11ea-9069-397e50b29005.png)

2. Ensure you have Microsoft Azure access – you should have this from MMAI 863.  Try your login [here](https://studio.azureml.net/)  

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

![Upload new dataset](https://user-images.githubusercontent.com/55206834/87226944-467e0a80-c365-11ea-910f-a7d8660f9cc7.png)

* You now have your dataset loaded and ready to use

Your screen should now look like this:

![Final screen - Step 2](https://user-images.githubusercontent.com/55206834/86878442-e2ceb580-c0b6-11ea-9abd-44e5d2487f3c.png)

### **Step 3 – Setup your Sentiment Analysis Architecture**

We are now ready to set up our Architecture. At the end of the tutorial, your Architecture should look like this:

![Finished Architecture](https://user-images.githubusercontent.com/55206834/86887276-4d3b2200-c0c6-11ea-8a02-40dc24ebf9f8.png)

### **Step 3a – Create an Experiment**

* Click _EXPERIMENTS_ in the left-hand column
* Click the _+NEW_ in the bottom left of the workspace window

![New Experiment](https://user-images.githubusercontent.com/55206834/86878673-71433700-c0b7-11ea-8d5c-9ba6af8bbff8.png)

* At this point, you can either choose a Blank Experiment or Experiment template (if you want to start from an existing template)
* For the purposes of this tutorial, click _Blank Experiment_

![Blank Experiment](https://user-images.githubusercontent.com/55206834/86878900-f9294100-c0b7-11ea-8d0b-41536a934976.png)

* You will see this blank architecture on the screen guiding you in how to set up your experiment architecture:

![Blank Experiment](https://user-images.githubusercontent.com/55206834/86879120-72289880-c0b8-11ea-808d-afaa4959a87e.png)

Now it is time to start adding the modules to your experiment canvas.

### **Step 3b – Load Your Data**

* From the left-hand menu, Click on _Saved Datasets_
* Click on _My Datasets_
* Locate your dataset in My Datasets on the left-hand menu under My Datasets
* Drag & Drop the Dataset to the right-hand side where your architecture canvas is

![Drag and Drop](https://user-images.githubusercontent.com/55206834/86700724-58675280-bfdf-11ea-912c-e499ab376e0f.png)

### **Step 3c – Pre-process your data** (3)

* In the _Search Experiment Items_ search box type in “_preprocess_”, 

![search](https://user-images.githubusercontent.com/55206834/86696966-f22d0080-bfdb-11ea-9878-e152865914d6.png)

* You will see _Preprocess Text_ Module under Text Analytics

![Preprocess](https://user-images.githubusercontent.com/55206834/86879692-7acd9e80-c0b9-11ea-90fd-582d727dbc3a.png)

* Drag and Drop _Preprocess Text_ to your canvas **below** your dataset box
* **Connect** the dataset to Preprocess Text module (left connector)

![Connect](https://user-images.githubusercontent.com/55206834/86879759-a486c580-c0b9-11ea-99f0-6f148aff8852.png)

* Set properties:
* > click on the _Preprocess Text_ module, and look at the right-hand column
* > Here you will see all the available pre-processing options to select from
* > Select the type of preprocessing you would like to do from the right-hand side of the screen
* > For the purposes of this tutorial, we accepted all the **default cleaning** as shown below:

![preprocess Properties](https://user-images.githubusercontent.com/55206834/86879972-03e4d580-c0ba-11ea-8213-97f2d0f73938.png)

![warning](https://user-images.githubusercontent.com/55206834/86663588-df0a3880-bfbb-11ea-9353-07aaba61152f.png)  Although we selected the default values for data preprocessing in our tutorial, remember that too much preprocessing can negatively impact your data classification results. Please make sure you do data analysis before determining which are the most appropriate preprocessing options to apply. 

* > Click _Launch Column selector_

![launch column selector](https://user-images.githubusercontent.com/55206834/86697725-a7f84f00-bfdc-11ea-8efc-c5101ada4a56.png)

* > Click _By Name_ on the left-hand side
* > Select only the _Sentence_ field and move it to the right-hand side under _SELECTED COLUMNS_ using the arrow in the center indicating you want to be pre-processed 
**Note**: Polarity should remain on the left-hand side under _AVAILABLE COLUMNS_
* Click on the _checkmark_

![Sentence](https://user-images.githubusercontent.com/55206834/86880454-b87ef700-c0ba-11ea-815e-c9af4f265b23.png)

* Run the module by right-clicking on the module and selecting _Run Selected_ from the menu

![Run selected](https://user-images.githubusercontent.com/55206834/86880863-570b5800-c0bb-11ea-893d-975f0efaaa1f.png)
 
* You will know it completed properly by the green checkmark that shows up in your _Preprocess Text_ module on your canvas

![Run Success](https://user-images.githubusercontent.com/55206834/86654388-e9283900-bfb3-11ea-89f3-34c8a1bb2797.png)


### **Step 3d – Vectorization**

The next step is to extract features you want to use using feature hashing. Hashing is how Microsoft Azure ML converts plain text to a vector (a set of integer features). It creates a dictionary of n-grams and calculates the frequency of terms and is based off the [Vowpal Wabbit framework](https://github.com/VowpalWabbit/vowpal_wabbit/wiki). (5)

* In the search box, enter “_feature_”, and you see _Feature Hashing_ Module under _Text Analytics_ in the left-hand menu

![Feature hashing](https://user-images.githubusercontent.com/55206834/86881271-021c1180-c0bc-11ea-8234-1d5bd4465900.png)

* Drag and Drop _Feature Hashing_ from the left-hand menu to your canvas under the _Preprocess Text_ module
* Connect the output of the _Preprocess Text_ module to the input of the _Feature Hashing_ module

![Connect hashing](https://user-images.githubusercontent.com/55206834/86882252-f5002200-c0bd-11ea-896d-062e7ccfb6fd.png)

* Click on the _Feature Hashing_ module on your canvas
* Click _Launch column selector_ from the right-hand menu to select the features you want to include
* Click on _BY NAME_ on the left-hand side
* Select _Preprocessed Sentence_ and move it to the right-hand side under _SELECTED COLUMNS_ using the arrow in the center 
Note: all other fields should be on the left-hand side under _AVAILABLE COLUMNS_
* Click on the _checkmark_

![Select preprocessed Sentence](https://user-images.githubusercontent.com/55206834/86881751-00068280-c0bd-11ea-91ae-b1b3bc05b9e6.png)

* Set the properties you want to use to vectorize the data
* For the purposes of this tutorial, we have used hashing bitsize of 8 with n-grams of 1. We selected n-grams of 1 because our dataset is not very diverse: it contains only reviews on food, products and movies. We were concerned that setting the n-grams higher than 1 (e.g. bigrams) would prevent the model from generalizing well on different types of tweets during deployment. For example, if we had used something like trigrams, there is a risk that the new test data would not have similar trigrams. The resulting vectorized test set would be extremely sparse resulting in poor results. If the dataset size was drastically increased, you can select a higher value for n-grams to embed context in your vector space.

![Hash Properties](https://user-images.githubusercontent.com/55206834/86881969-72776280-c0bd-11ea-8220-1a24db5eb3b5.png)

* _Run_ the _Feature Hashing_ module by right-clicking on it and selecting _Run selected_ (remember to look for the green checkmark  on your module indicating a successful run before moving on)

### **Step 3e – Select the data to pass to your model**

After running the feature hashing module, we now have preprocessed data and vectorized the features. We need to select those features and the target feature to pass to our ML algorithm.

There is a _Select Columns in Dataset_ module available to assist us with this.
* In the search box, enter “_select_”, and you see _Select Columns in Dataset_ Module under Data Transformation

![search select cols](https://user-images.githubusercontent.com/55206834/86882672-a8691680-c0be-11ea-803a-57c265b11f41.png)

* Drag and Drop _Select Columns in Dataset_ to your canvas
* Connect the _Feature Hashing_ module to _Select Columns in Dataset_

![Connect](https://user-images.githubusercontent.com/55206834/87174480-3868b500-c2a5-11ea-8436-457f53d05f78.png)

* Set properties by clicking on the module, and then clicking on _Launch column selector_
* Select the required columns for ML to use (In our case study, we **exclude** the columns “_Sentence_” and “_Preprocessed Sentence_”)
* > Click on WITH RULES on the left-hand side
* > Select **Begin with: all columns** and **Exclude** the **column names** _Sentence_ and _preprocessed sentence_) *remember your ML algorithm doesn’t understand plain text so it only wants the vectorized data
* > Click on the _checkmark_

![select columns](https://user-images.githubusercontent.com/55206834/86883169-80c67e00-c0bf-11ea-983f-4adfcabc7f4f.png)

You should now see this above _Launch column selector_:

![hash select cols](https://user-images.githubusercontent.com/55206834/86705854-4936d380-bfe4-11ea-996a-7ad9170a6d5b.png)

* _Run_ the _Select Columns in Dataset_ module by right-clicking on it and selecting _Run selected_ (remember to look for the green checkmark of a successful run before moving on)

### **Step 3f – Split your data into training and testing data** (6)

We will use Azure’s built-in Split Data module.
* In the search box, enter “_split_”, and you see _Split Data_ Module under _Data Transformation/Manipulation_

![split](https://user-images.githubusercontent.com/55206834/86883411-efa3d700-c0bf-11ea-9801-c63aa85bc55b.png)

* Drag and Drop the _Split Data_ module to your canvas
* **Connect** the _Select Columns_ in Dataset module to _Split Data_

![Connect](https://user-images.githubusercontent.com/55206834/86883560-2d086480-c0c0-11ea-9b32-661978d122f0.png)

* Set properties by clicking on the _Split Data_ module
* > In our example we split the data into _80% training_ data and _20% testing_ data by setting the _Fraction of rows in the first_ to 0.8
* > _Check the box_ for _Randomized split_
* > Set your _Random seed_ = 42 so that your results are reproduceable
* > Set _Stratified split_ to _True_

![split properties](https://user-images.githubusercontent.com/55206834/86884158-29c1a880-c0c1-11ea-9ec8-dd4bc367181f.png)

**Note**: Once you set _Stratified split_ to _True_, The _Launch column selector_ option will appear in the right-hand column

You now want to select a single column for the stratification. In our instance: _Polarity_
* > Click on _Launch column selector_
* > Click on _BY NAME_
* > Click on _Polarity_ in the left-hand column and move it to the right-hand column under _SELECTED COLUMNS_ using the arrow in the middle
* > Click on the _checkmark_

![stratified split](https://user-images.githubusercontent.com/55206834/86884596-cb48fa00-c0c1-11ea-8824-39efd8217e5f.png)

* _Run_ the _Stratified split_ module by right-clicking on it and selecting _Run selected_ (remember to look for the green checkmark of a successful run before moving on)

We now have our dataset ready for training. 

### **Step 3g – Select and train your model** (7)

Instantiate your model by selecting the classification algorithm. For the purposes of this tutorial, we will be using a Two-Class Boosted Decision Tree because it is easy to implement and typically achieves good performance. Using a boosted decision tree allows you to improve upon the results of your decision tree model over multiple iterations. It then makes predictions based on the entire ensemble of trees. (8)

![warning](https://user-images.githubusercontent.com/55206834/86663588-df0a3880-bfbb-11ea-9353-07aaba61152f.png) This type of model is very memory intensive as it holds everything in the current implementation in memory. You must pay special attention to the model training speed as the dataset starts to increase in size if you choose this model in a real-life scenario. This is not a concern for this tutorial as our dataset is very small.

For further information, please refer to this [link](https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/two-class-boosted-decision-tree) from Microsoft on Two-Class Boosted Decision Trees.

* In the search box, enter “_classification_”, and you see the classification algorithms available
* Choose your algorithm. In our tutorial, we will be using _Two-class Boosted Decision Tree_
* Drag and Drop the _Two-class Boosted Decision Tree_ classifier to your canvas 

![search DT](https://user-images.githubusercontent.com/55206834/86884935-62ae4d00-c0c2-11ea-95e7-eebf11cd3277.png)

* In the search box, enter “_Train_” to select the _Train Model_ module
* Drag and Drop the _train model_ module to your canvas beside your _Split Data_ module

![search train](https://user-images.githubusercontent.com/55206834/86885225-e10aef00-c0c2-11ea-98df-a16441ab1f6b.png)

* Connect _Two-class Boosted Decision Tree_ to the left input node of _Train Model_
* Connect the Training Dataset (left output node of _Split Data_ module) to the right input node of the _Train Model_ module

![train model connect](https://user-images.githubusercontent.com/55206834/86891447-dd7c6580-c0cc-11ea-8c47-3bb3e377cc21.png)

* Set training properties by clicking on the module _Train Model_ 
* Click on _Launch Column Selector_ 
* > Click on _BY NAME_
* > Select the _Polarity_ column on the right-hand side and move it to the left-hand side under _SELECTED COLUMNS_ using the arrow in the middle
* > Click on the _checkmark_

![select train cols](https://user-images.githubusercontent.com/55206834/86885555-7d34f600-c0c3-11ea-9300-1fdef642ac61.png)

Set the properties for your model.
* Click on your _Two-Class Boosted Decision Tree_ module and set the parameters on the left-hand side
* In our tutorial, we used the default settings of:
* > Max number of leaves = 20
* > Min number of samples = 10
* > Learning rate = 0.2
* > Number of trees constructed = 100
* > Random number seed = 42

![DT properties](https://user-images.githubusercontent.com/55206834/86885826-ec124f00-c0c3-11ea-8227-76d9e4e017f7.png)

![warning](https://user-images.githubusercontent.com/55206834/86663588-df0a3880-bfbb-11ea-9353-07aaba61152f.png)  Beware of using the default values in real-world applications as you can end up with large decision trees that overfit your model and do not generalize well during deployment. Although we are only showing you one model with no hyperparameter tuning in this tutorial, it is recommended that you test several models and perform hyperparameter tuning in real-world scenarios. In order to understand further how to do the latter in Azure ML Studio, please follow this [link](https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/tune-model-hyperparameters).

* _Run_ the _Train Model_ module by right-clicking on it and selecting _Run Selected_ (remember to look for the green checkmark of a successful run before moving on)

The model training is now complete. 

### **Step 3h – Evaluate your model’s performance**

* In the search box, enter “_score_”, and you see _Score Model_ module
* Drag and Drop the _Score Model_ module to your canvas

![search score](https://user-images.githubusercontent.com/55206834/86886145-67740080-c0c4-11ea-817a-438721f2c362.png)

* In the search box, enter “_Evaluate_”, and you see _Evaluate Model_ module
* Drag and Drop the _Evaluate Model_ module to your canvas

![search evaluate](https://user-images.githubusercontent.com/55206834/86886314-b326aa00-c0c4-11ea-9855-ae646611a4b8.png)

* Connect the output node of _Train Model_ to the left input node of _Score Model_
* Connect _Split Data_ (right output node) to the right input node of _Score Model_
* Connect _Score Model_ to _Evaluate Model_

![connect score](https://user-images.githubusercontent.com/55206834/86886558-24665d00-c0c5-11ea-8b9c-eec11fead081.png)

* _Run_ the _Evaluate Model_ module by right-clicking on it and selecting _Run selected_ (remember to look for the green checkmark of a successful run before moving on)
* You can now visualize your results by right-clicking on _evaluate model_ and selecting _Evaluation Results_ -> _Visualize_

![visualize menu](https://user-images.githubusercontent.com/55206834/86886795-8757f400-c0c5-11ea-977c-185ffa637b29.png)

![F1 Score](https://user-images.githubusercontent.com/55206834/87107541-036d4b80-c22e-11ea-9264-327141ec0865.png)

## **Analyze results**

We chose to look at F1 score for our model as our dataset was fairly well balanced. F1 score is the harmonic mean of precision and recall. It will be more sensitive to the weaker of the two metrics, which makes the F1 score a conservative estimate of the model performance. Our model had an F1 score of 0.717 which is not too bad for a quick first attempt at sentiment analysis considering our dataset contains two different types of tweets (food/product and movie reviews). We would not, however, recommend rolling this out as-is because the impact of misclassifying a tweet is too large (28%). Translating this to business terms, I would predict that 79 people liked my restaurant/movie/product when, in fact, they did not. This error would lead me into a false sense of security instead of prompting me to improve my business, which could have a disastrous impact. 

You can now compare the results you achieved in this tutorial to the results of your NLP Individual Assignment. Feel free to play around with the tutorial and change the pre-processing you do on your data, the model you use and the hyperparameter tuning/model parameters. 

## **Deploying your model** (9)

When you are satisfied with your model, it is time to deploy it to production.  

## **Step 1 - Convert the training experiment to a Predictive experiment**

* Click _SET UP WEB SERVICE_ and then _Predictive web service (recommended)_

![setup web service](https://user-images.githubusercontent.com/55206834/86718092-c49e8200-bff0-11ea-8288-ff89d6e6c835.png)

![warning](https://user-images.githubusercontent.com/55206834/86663588-df0a3880-bfbb-11ea-9353-07aaba61152f.png) At this point, if you don’t see the _SET UP WEB SERVICE_ option, you may not have run your full experiment, please go back and do so now and try again.

You will now see a second tab with your Predictive experiment.

![Predictive experiment](https://user-images.githubusercontent.com/55206834/86887636-dbafa380-c0c6-11ea-8161-3e1c36ad6e4c.png)

* Select _RUN_ from the bottom menu to run the full model

![run](https://user-images.githubusercontent.com/55206834/86719837-712d3380-bff2-11ea-8ed1-2e790445bb43.png)

* Right-click on the _Score Model_ module and select _Scored Dataset_ and then _Visualize_ to ensure it has all the vectorized data (similar to the experiment data view)

![scored dataset](https://user-images.githubusercontent.com/55206834/86720831-66bf6980-bff3-11ea-9fd5-34716405a02c.png)

* The Score Model will contain all the features used to train the model plus 2 other features (Scored Labels, and Scored Probabilities) 
* In the search in the left-hand column, type "select columns"

![select cols](https://user-images.githubusercontent.com/55206834/86887945-642e4400-c0c7-11ea-8025-4ec424c1df6c.png)

* Drag and Drop _Select Columns in Dataset_ module to the Predicted experiment canvas placing it between the _Score Model_ and _Web service output_ 

![add select cols](https://user-images.githubusercontent.com/55206834/86888107-a5beef00-c0c7-11ea-9a51-ea11659fdd95.png)

* Reconnect the _Score Model_ output node to the _Select Columns in Dataset_ input node
* Connect the _Select Columns in Dataset_ output node to the _Web service output_ top (input) node

![select cols connected](https://user-images.githubusercontent.com/55206834/86888233-d69f2400-c0c7-11ea-9afb-fbb91da301bf.png)

* Click on _Select Columns in Dataset_ module
* Click on _Launch column selector_ 
* Click on BY NAME on the right-hand side
* Scroll all the way down the AVAILABLE COLUMNS column on the left to find **Scored Labels** and **Scored Probabilities** and select them both (click first, hold down shift and click the second)
* Move them to the right-hand Selected columns column by clicking the arrow in the middle

![select scored cols](https://user-images.githubusercontent.com/55206834/86888591-69d85980-c0c8-11ea-9e03-ee94bd903f25.png)

* Click on the _checkmark_

![deploy scored cols 2](https://user-images.githubusercontent.com/55206834/86888723-a6a45080-c0c8-11ea-9faa-e8fd34458245.png)

* _Run_ the Predictive experiment again by selecting _Run_ from the bottom menu 

![run](https://user-images.githubusercontent.com/55206834/86719837-712d3380-bff2-11ea-8ed1-2e790445bb43.png)

The Web service can now be deployed 

## **Step 2 - Deploy**

* Click _DEPLOY WEB SERVICE_ 

![deploy web service](https://user-images.githubusercontent.com/55206834/86889201-609bbc80-c0c9-11ea-8354-57b836613ccb.png)

## **Step 3 – Test**

* You can test your newly created web service by selecting _New Web Service Experience_

![Test_New Web Services Experience](https://user-images.githubusercontent.com/55206834/86998303-19bbce80-c17e-11ea-9a24-3ea85109e140.png)

* Click on _Test Endpoint_

![Test Endpoint](https://user-images.githubusercontent.com/55206834/87109651-3cf48580-c233-11ea-82f6-4fe16ae8f7b8.png)

You will see a screen to test your web service.  
* Type in some text in the Sentence field and click on the _Test Request Response_ 
Your result will appear on the right-hand side of the screen.

Example of positive sentiment test:

![Positive test sentence](https://user-images.githubusercontent.com/55206834/87110143-54803e00-c234-11ea-84ab-eb4f5ce8e6b9.png)

Output:

![Positive test output](https://user-images.githubusercontent.com/55206834/87110097-387c9c80-c234-11ea-8c29-e63364152083.png)

Example of negative sentiment test:

![Negative test sentence](https://user-images.githubusercontent.com/55206834/87110250-898c9080-c234-11ea-920c-d66f46ee161f.png)

Output:

![Negative test output](https://user-images.githubusercontent.com/55206834/87110198-711c7600-c234-11ea-9f01-a4eff1e679c1.png)

# **Calling your Web Service from Python**

You can find all the information you need to call your web service from an application by navigating back to the _New Web Services Experience_ page and selecting _Use Endpoint_.

![Use Endpoint](https://user-images.githubusercontent.com/55206834/87115151-74b5fa00-c240-11ea-854a-aae5fa80bb4a.png)

This screen will give you all your access keys and give you sample code to get you started.

![Sample Code](https://user-images.githubusercontent.com/55206834/87115080-39b3c680-c240-11ea-9ee4-6935bfd55d27.png)

# **Conclusion**

We started this exercise with a business problem to solve: create a sentiment analysis tool to predict whether tweets related to your products and services are positive or negative.

Now that you have quickly built a sentiment analysis experiment, you can impress your new boss with an example of the art-of-the-possible. If this is well received and a business case can be made to implement this type of solution, you can refine your model and when you are happy with your results you can easily extend it for use as an API in a custom-built script for free (for up to 1,000 transactions). You can link to it using the Excel add-in (10) and allow your customer experience team to have direct access to it or you could create an application that references the API to:

* Scrapes tweets (11)
* Classifies them as positive or negative 
* Generates reports on that data for your customer experience team

We hope you enjoyed this tutorial and that you have a better understanding of how you can easily use Microsoft Azure ML to do Sentiment Analysis quickly and easily.

**Other reference material:**

(1) for more information on setting up your workspace, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/create-workspace

(2) For another tutorial example, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/tutorial-part1-credit-risk

(3) To learn more about preprocessing data in Azure ML studio, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/preprocess-text?redirectedfrom=MSDN

(4) To learn more about the hashing function, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/feature-hashing?redirectedfrom=MSDN

(5) For more information on hashing, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-module-reference/feature-hashing#:~:text=Use%20the%20Feature%20Hashing%20module,based%20on%20the%20nimbusml%20framework.

(6) To learn more about how to split data in Azure ML, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/split-data?redirectedfrom=MSDN

(7) To learn more about training models, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/train-model?redirectedfrom=MSDN

(8) For more information on Two-Class Boosted Decision Trees, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio-module-reference/two-class-boosted-decision-tree

(9) For more information on web services, please refer to: https://services.azureml.net/subscriptions/9887b0c8-8f21-4ab3-9265-d4e879c54888/resourceGroups/bamservice/providers/Microsoft.MachineLearning/webServices/Sentiment2create.2020.7.3.22.56.47.8/test/rrs

(10) For more information on how to use Excel to access your Azure ML web service, please refer to: https://docs.microsoft.com/en-us/azure/machine-learning/studio/excel-add-in-for-web-services

(11) For more information on how to scrape tweets, please go to: https://dev.twitter.com/apps/new and sign up for a developer account and you will find a lot of useful information there





