# **Business Problem**

You are a recent graduate of the Smith School of Business MMAI program and have just been hired into the Data Science team at Bathurst Inc. You have been tasked to create a sentiment analysis tool to predict whether tweets related to your products and services are positive or negative for the purposes of:

* Providing the customer experience team with “strong positive” tweets so they can generate an outbound marketing campaign to get promoters to provide online recommendations and strengthen the company’s online presence
* Providing the customer retention team with “strong negative” tweets so they can address the issues with the customers and turn detractors into (at worst) neutral, (at best) promoters of the company

Despite being a strong coder, you have not been part of deploying an end-to-end machine learning project. Therefore, you are looking for a Platform-as-a-Service (PaaS) that has high flexibility, fast training speed, high accuracy, and is user friendly.

# **An Overview of PaaS**

PaaS is a category of cloud computing services that provides a platform (a medium to use) for customers to develop, run, and manage applications with simplicity. PaaS is especially powerful for developing and launching apps without requiring the complexity of building and maintaining the infrastructure that is typically required.

## **Top PaaS Vendors**

The PaaS space is largely dominated by three companies (as of year ending in June 2019) (1):
1. Amazon's market-leading AWS offering with 23.6% of the market   
2. Microsoft's Azure platform with 17% of the market
3. Google Cloud with 7.1% of the market 

## **Why Azure?**

A breakdown of the machine learning subsets within these top three PaaS providers are highlighted in Table 1 below (2). From this table, it can be observed that Microsoft Azure Machine Learning (ML) Studio scores the highest overall in terms of flexibility, usability, and accuracy maintaining a low training time, which meets our expectations outlined in the business problem. A brief explanation of why ML Studio does so well is below:

* It is a fully managed collaborative drag-and-drop dashboard tool, which makes it easy to quickly learn and use
* It publishes models as web services that can easily be consumed by custom apps or BI tools such as Excel (3)
* It contains standard experiment templates, which allow users to obtain results quickly

![Table 1 - Main ML Market Players Comparison](https://user-images.githubusercontent.com/55206834/86994708-14a65180-c175-11ea-818d-f666f8a97912.png)

## **Azure Text Analytics Functionality & Use Cases**

ML Studio’s Text Analytics API is specifically designed for text related business cases such as classifying your tweet dataset. The four analysis tools within this API are found below with example use cases (4).  

### _Sentiment Analysis_ <-- **This is what your business use case requires**

The use of natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information.

Example Use Cases: 
* Identifying customer insights to predict or prevent things like churn
> Monitor social media feeds <-- **this is the one we will examine in our tutorial**

> Analyzing customer satisfaction survey results (uses key phrase extraction as well)

> Analyzing recorded inbound customer calls (uses key phrase extraction as well)

### _Key Phrase Extraction_

Example Use Case:
* Optimize support to save money
> Process and categorize support incidents

### _Named Entity Recognition_

Example Use Case:
* Documentation management & compliance
> Classify and redact documents that have sensitive information

### _Language Detection_

Example Use Case:
* Document Management
> Classify a corpus of documents by language or dialect

More information on each of these tools can be found [ here]( https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/overview) (5).

# **Azure for Sentiment Analysis**

In conclusion, Azure’s ML Studio is well suited for the business problem you have been given: using sentiment analysis to classify tweets. This specific PaaS is user friendly and provides the end-to-end ability for you to build, test and deploy predictive analytics solutions on your data. The Text Analytics API within ML Studio is extremely powerful and already contains pre-existing Sentiment Analysis tools and experiments, which can expedite project implementation. 

Good luck with running your [tutorial](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis/wiki/Microsoft-Azure-ML-Studio---Sentiment-Analysis-Tutorial). Remember to check the [FAQs](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis/wiki/FAQs) if you run into issues.


**References:**

(1) https://www.statista.com/statistics/1052864/worldwide-iaas-paas-vendor-share/

(2) https://www.slideshare.net/ivoandreev/azure-machine-learning-and-ml-on-premises (slide 10)

(3) https://www.mercurysolutions.co/blog/top-11-business-benefits-of-microsoft-azure 

(4) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/text-analytics-user-scenarios

(5) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/overview

