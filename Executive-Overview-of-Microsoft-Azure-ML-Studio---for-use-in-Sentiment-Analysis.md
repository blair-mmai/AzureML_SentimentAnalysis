This section is written to help an executive understand the basics of Platform-as-a-service (PaaS) solution, the different cloud offerings on the market, and associated costs/benefits of Microsoft Azure more specifically.

# **Executive Overview**

## **Cloud and AI - An Overview**

PaaS is a category of cloud computing services that provides a platform (a medium to use) for customers to develop, run, and manage applications with simplicity. PaaS is especially powerful for developing and launching Apps without requiring the complexity of building and maintaining the infrastructure that is typically required.

The PaaS space is led by 3 companies. Amazon with a market-leading AWS offering, Microsoft with Azure as the second-largest (1) PaaS at 17.6% (2) of the market in February of 2020, and Google with a 3rd place cloud offering at roughly 10% market share. All three of these market leaders offer value as a PaaS as seen in Figure 1 below (3) and have different pricing models as seen in Figure 2 below (3).

![Figure 1 Main ML Market Players Comparison](https://user-images.githubusercontent.com/55206834/86639331-baf02c80-bfa6-11ea-968a-397367814acd.png)

Figure 1 Main ML Market Players Comparison

![Figure 2 PaaS Pricing](https://user-images.githubusercontent.com/55206834/86639783-82048780-bfa7-11ea-97f9-9f9e05126edb.png)

Figure 2 Pricing for Market Players

PaaS through Azure as a common platform simplifies training and integration across organizations in a cost-effective way. Azure and other PaaS Services are typically paid for by usage, therefore, allowing rapid scaling (4) in a manner that is cost-effective. 

Looking specifically at Text Analytics capabilities, the table below does a good job of summarizing the capabilities you will find across the various PaaS platforms (5):
 
![Figure 3 Comparison of NLP Services](https://user-images.githubusercontent.com/55206834/86625341-f254de00-bf92-11ea-81a8-f0297571805d.png)

Figure 3 Comparison of NLP Services

Given Bathurst Inc. is trying to understand it's customer's sentiment in our tutorial example, we explore Azure specifically for Sentiment Analysis below as our platform of choice. 

## **Azure Machine Learning Studio**

Microsoft Azure Machine Learning (ML) Studio is a collaborative, drag-and-drop tool that exists in the Azure PaaS world. you can use ML Studio to build, test, and deploy predictive analytics solutions on your data. Azure ML Studio publishes models as web services that can easily be consumed by custom apps or BI tools such as Excel (6). 

There are several benefits of using Azure ML Studio (7): 
1. It is easy to quickly learn and use with drag-and-drop capabilities
2. Standard experiments allow for a starting point and allow users to get quick results
3. It is a fully managed service   
 
## **Pricing**

Pricing is offered under two main tiers (8) for the Azure ML studio.
 
![Figure 4 Azure ML Studio Pricing](https://user-images.githubusercontent.com/55206834/86628112-685b4400-bf97-11ea-9ea2-26d257612fac.png)

Figure 4 Azure ML Studio Pricing

In addition to the tiered pricing for access to the ML studio, compute power and space are charged on an hourly or reserved basis. The cost for state-of-the-art computing power capable of running deep neural networks through multiple concurrent users may cost as high as $138,000 annually (see Figure 5), however, in most instances, costs may be less than the cost of purchasing an on-premise server. This pricing (9) information can be applied to real-world solutions using the easily accessible cost calculator available online.

![Figure 5 Virtual Machines Estimated Costs](https://user-images.githubusercontent.com/55206834/86641606-44086300-bfa9-11ea-8a45-2ce7a3fce9ae.png)

Figure 5 Virtual Machines Estimated Costs

Finally, API costs for using Azure PaaS should also be considered depending on the use case (10). Generally speaking, costs for API usage scale up with the number of transactions and compute hours required.

![Figure 6 Azure API Costs](https://user-images.githubusercontent.com/55206834/86641866-73b76b00-bfa9-11ea-914a-71c0c18b5b70.png)

Figure 6 Azure API Costs
 
## **Using ML Studio & Text Analytics API**

The Text Analytics API can be used for four (4) types of Analysis (11), however, our focus for this tutorial will be on Sentiment Analysis.

1. Sentiment Analysis (12)  
> the use of natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information
2. Key Phrase Extraction (13)
> Keyword extraction is tasked with the automatic identification of terms that best describe the subject of a document. Key phrases, key terms, key segments or just keywords are the terminology which is used for defining the terms that represent the most relevant information contained in the document
3. Language Detection (14)
> In natural language processing, language identification or language guessing is the problem of determining which natural language given content is in. Computational approaches to this problem view it as a special case of text categorization, solved with various statistical methods
4. Named Entity Recognition (15) 
> Named-entity recognition is a subtask of information extraction that seeks to locate and classify named entities mentioned in unstructured text into pre-defined categories such as person names, organizations, locations, medical codes, time expressions, quantities, monetary values, percentages, etc.

There are several business use cases for Text Analytics API services, such as (16): 

* Identifying customer insights to predict or prevent things like churn:
* > Analyzing customer satisfaction survey results 
* > Analyzing recorded inbound customer calls
* > **Monitor social media feeds** <-- this is the one we will examine in our tutorial
* > Opinion mining

* Optimize Support to save money:
* > Process and categorize support incidents

* Documentation Management & Compliance:
* > Classify and redact documents that have sensitive information

Azure ML studio has pre-defined experiments so that even with little to no programming experience, you can run an ML experiment. Ready to give it a try? Follow the step by step tutorial on our [Tutorial page](https://github.com/cShellinc/AzureMLTutorial_SentimentAnalysis/wiki/Microsoft-Azure-ML-Studio---Sentiment-Analysis-Tutorial).

References used:
(1) https://www.zdnet.com/article/the-top-cloud-providers-of-2020-aws-microsoft-azure-google-cloud-hybrid-saas/ 
(2) https://www.parkmycloud.com/blog/aws-vs-azure-vs-google-cloud-market-share/ 
(3) https://www.slideshare.net/ivoandreev/azure-machine-learning-and-ml-on-premises
(4) https://www.youtube.com/watch?v=KXkBZCe699A 
(5) https://medium.com/kontikilabs/comparing-machine-learning-ml-services-from-various-cloud-ml-service-providers-63c8a2626cb6 
(6) https://docs.microsoft.com/en-us/azure/machine-learning/studio/what-is-ml-studio#:~:text=Microsoft%20Azure%20Machine%20Learning%20Studio,BI%20tools%20such%20as%20Excel
(7) https://www.codit.eu/blog/azure-machine-learning-studio-vs-services/?country_sel=be
(8) https://azure.microsoft.com/en-us/pricing/details/machine-learning-studio/
(9) https://azure.microsoft.com/en-us/pricing/calculator/
(10) https://www.google.com/search?q=azure+api+cost&rlz=1C1CHBF_enCA862CA862&oq=azure+api+cost&aqs=chrome..69i57.3521j0j4&sourceid=chrome&ie=UTF-8
(11) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/overview
(12) https://en.wikipedia.org/wiki/Sentiment_analysis
(13) https://en.wikipedia.org/wiki/Keyword_extraction
(14) https://en.wikipedia.org/wiki/Language_identification
(15) https://en.wikipedia.org/wiki/Named-entity_recognition
(16) https://docs.microsoft.com/en-us/azure/cognitive-services/text-analytics/text-analytics-user-scenarios

