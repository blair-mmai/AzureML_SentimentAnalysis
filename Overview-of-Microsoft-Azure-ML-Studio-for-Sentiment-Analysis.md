# **Business Problem**

You are a recent graduate of the Smith School of Business MMAI program and have just been hired into the Data Science team at Bathurst Inc., a movie theatre and restaurant. You have been tasked to create a sentiment analysis tool to predict whether tweets related to your products and services are positive or negative for the purposes of:

* Providing the customer experience team with “strong positive” tweets so they can generate an outbound marketing campaign to get promoters to provide online recommendations and strengthen your online presence
* Providing the customer retention team with “strong negative” tweets so they can address the issues with the customers and turn detractors into (at worst) neutral, (at best) promoters of the company

Despite being a strong coder, you have not been part of deploying an end-to-end machine learning project. Therefore, you are looking for a Platform-as-a-Service (PaaS) that has high flexibility, fast training speed, high accuracy, and is user friendly in order to get this up and running quickly.

# **An Overview of PaaS**

PaaS is a category of cloud computing services that provides a platform (a medium to use) for customers to develop, run, and manage applications with simplicity. PaaS is especially powerful for developing and launching apps without requiring the complexity of building and maintaining the infrastructure that is typically required.

## **Top PaaS Vendors**

The PaaS space is largely dominated by three companies (as of year ending in June 2019) (1):
1. Amazon with a market-leading AWS offering and 23.6% of the market   
2. Microsoft with Azure with 17% of the market
3. Google Cloud with 7.1% of the market 

## **Why Azure?**

A breakdown of the Machine Learning subsets within these top three PaaS providers are highlighted below in Table 1 (2). From this table, it can be observed that Microsoft Azure Machine Learning (ML) Studio scores the highest overall in terms of flexibility, usability, and accuracy while maintaining a low training time. A brief explanation of why ML Studio does so well is below:

1. ML Studio is a fully managed collaborative drag-and-drop dashboard tool, which makes it easy to quickly learn and use
2. Additionally, it publishes models as web services that can easily be consumed by custom apps or BI tools such as Excel (3)
3. Finally, ML Studio contains standard experiment templates, which allow users to obtain results quickly

## **Azure Text Analytics Functionality & Use Cases**

ML Studio’s Text Analytics API is specifically designed for text related business cases such as classifying our tweet dataset. The four analysis tools within this API are found below with example use cases (4).  

_Sentiment Analysis_ <-- **This is what your business use case requires**

The use of natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information.

**Example Use Cases:** 
* Identifying customer insights to predict or prevent things like churn
*** Monitor social media feeds <-- this is the one we will examine in our tutorial**
* Analyzing customer satisfaction survey results (uses key phrase extraction as well)
* Analyzing recorded inbound customer calls (uses key phrase extraction as well)

_Key Phrase Extraction_

**Example Use Case:** 
* Optimize support to save money
* > Process and categorize support incidents

_Named Entity Recognition_

**Example Use Case: **
* Documentation Management & Compliance
> * Classify and redact documents that have sensitive information

_Language Detection _

**Example Use Case: **
* Document Management
> * Classify a corpus of documents by language or dialect

More information on each of these tools can be found [ here]( https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/overview) (5).

# **Azure for Sentiment Analysis**

In conclusion, Azure’s ML Studio is well suited for the business problem we are presented with: using sentiment analysis to classify tweets. This specific PaaS is user friendly and provides the end-to-end ability for users to build, test and deploy predictive analytics solutions on their data. The Text Analytics API within ML Studio is extremely powerful and already contains pre-existing Sentiment Analysis tools and experiments, which can expedite project implementation. 

Good luck with running your tutorial. Remember to check the FAQs if you run into issues.


**References:**
(1) https://www.statista.com/statistics/1052864/worldwide-iaas-paas-vendor-share/

(2) https://medium.com/kontikilabs/comparing-machine-learning-ml-services-from-various-cloud-ml-service-providers-63c8a2626cb6 

(3) https://www.mercurysolutions.co/blog/top-11-business-benefits-of-microsoft-azure 

(4) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/text-analytics-user-scenarios

(5) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/overview

