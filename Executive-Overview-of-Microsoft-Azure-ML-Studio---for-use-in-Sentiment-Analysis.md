Welcome to the AzureMLTutorial_SentimentAnalysis wiki! Below you will find an Executive Overview of 

# **Executive Overview**

## **Cloud and AI - An Overview**

This section is written to help an executive understand the basics of Platform-as-a-service (PaaS) solution, the different cloud offerings on the market, and associated costs/benefits of Microsoft Azure more specifically.

PaaS is a category of cloud computing services that provides a platform (a medium to use) for customers to develop, run, and manage applications with simplicity. PaaS is especially powerful for developing and launching Apps without requiring the complexity of building and maintaining the infrastructure that is typically required.

The PaaS space is led by 3 companies. Amazon with a market-leading AWS offering, Microsoft with Azure as the second-largest (1) PaaS at 17.6% (2) of the market in February of 2020, and Google with a 3rd place cloud offering at roughly 10% market share. All three of these market leaders offer value as a PaaS (3), however, our focus will be on the Azure platform developed by Microsoft for this tutorial.

![Figure 1 Main ML Market Players Comparison](https://user-images.githubusercontent.com/55206834/86638678-c0994280-bfa5-11ea-9907-e40b3afcb4c7.jpeg)

Figure 1 Main ML Market Players Comparison

PaaS through Azure as a common platform simplifies training and integration across organizations in a cost-effective way. Azure and other PaaS Services are typically paid for by usage, therefore, allowing rapid scaling (4) in a manner that is cost-effective. 

Looking specifically at Text Analytics capabilities, the table below does a good job of summarizing the capabilities you will find across the various PaaS platforms (5):
 
![Figure 2 Comparison of NLP Services](https://user-images.githubusercontent.com/55206834/86625341-f254de00-bf92-11ea-81a8-f0297571805d.png)

Figure 2 Comparison of NLP Services

Given Bathurst Inc. is trying to understand it's customer's sentiment in our tutorial example, we explore Azure specifically for Sentiment Analysis below as our platform of choice. 

## **Azure Machine Learning Studio**

Microsoft Azure Machine Learning (ML) Studio is a collaborative, drag-and-drop tool that exists in the Azure PaaS world. you can use ML Studio to build, test, and deploy predictive analytics solutions on your data. Azure ML Studio publishes models as web services that can easily be consumed by custom apps or BI tools such as Excel. 

There are several benefits of using Azure ML Studio: 
1. Ease of application management
> Organizations can manage all their applications that are on the Azure platform from the same easy to use interface
2. Flexibility to pay for use or pay as you go
> Organizations can pay only for what they need and scale when and if they need them without incurring significant up-front infrastructure costs
3. Agility to move quickly
> By managing their platform through the Azure interface and scaling when needed, organizations can innovate and more quickly scale their applications
4. Compliance to privacy standards
> By leveraging a platform as a service, organizations can take advantage of privacy standards that are part of the service, making it especially easy for sectors like finance and legal
5. Reliability in storing and sharing data
> The Azure platform has several data centers and delivery points making storage and sharing reliable and faster
6. Higher Security
> By leveraging a platform as a service, organizations can take advantage of security features that are embedded in the platform (like two-tier authentication and biometric readers) making solutions more secure
7. Built-in analytics support
> Azure has built-in analytics support
8. End to end delivery plan
> Azure has built-in source control, unit testing, delivery and go live tools
9. Disaster recovery
> Azure has built-in recovery capabilities including failover
10. Deployed anywhere
> Azure accepts a hybrid model and allows organizations to select their data storage making transition easy
11. Automatic updates
> Software updates are automated and real-time
 
## **Pricing**

Pricing is offered under two main tiers  for the Azure ML studio.
 
![Figure 3 Azure ML Studio Pricing](https://user-images.githubusercontent.com/55206834/86628112-685b4400-bf97-11ea-9ea2-26d257612fac.png)

Figure 3 Azure ML Studio Pricing


In addition to the tiered pricing for access to the ML studio, compute power and space are charged on an hourly or reserved basis. The cost for state-of-the-art computing power capable of running deep neural networks through multiple concurrent users may cost as high as $138,000 annually (see Figure 2), however in most instances, costs may be less than the cost of purchasing an on-premise server. This pricing information can be applied to real-world solutions using the easily accessible cost calculator available online.



Figure 3 Virtual Machines Estimated Costs


Finally, API costs for using Azure PaaS should also be considered depending on the use case . Generally Speaking, costs for API usage scale up with the number of transactions and compute hours required.


Figure 4 Azure API Costs
 
## **Using ML Studio & Text Analytics API**

The Text Analytics API can be used for four (4) types of Analysis, however, our focus for this tutorial will be on Sentiment Analysis.

1. Sentiment Analysis  
> the use of natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information
2. Key Phrase Extraction 
> Keyword extraction is tasked with the automatic identification of terms that best describe the subject of a document. Key phrases, key terms, key segments or just keywords are the terminology which is used for defining the terms that represent the most relevant information contained in the document
3. Language Detection 
> In natural language processing, language identification or language guessing is the problem of determining which natural language given content is in. Computational approaches to this problem view it as a special case of text categorization, solved with various statistical methods
4. Named Entity Recognition 
> Named-entity recognition is a subtask of information extraction that seeks to locate and classify named entities mentioned in unstructured text into pre-defined categories such as person names, organizations, locations, medical codes, time expressions, quantities, monetary values, percentages, etc.

There are several business use cases for Text Analytics API services, such as: 

* Identifying customer insights to predict or prevent things like churn:
> Analyzing customer satisfaction survey results 
> Analyzing recorded inbound customer calls
> Monitor social media feeds <-- this is the one we will examine in this tutorial
> Opinion mining

* Optimize Support to save money:
> Process and categorize support incidents

* Documentation Management & Compliance:
> Classify and redact documents that have sensitive information

Azure ML studio has pre-defined experiments so that even with little to no programming experience, you can run an ML experiment. Ready to give it a try? Follow the step by step tutorial on our Tutorial page.

References used:
(1) https://www.zdnet.com/article/the-top-cloud-providers-of-2020-aws-microsoft-azure-google-cloud-hybrid-saas/ 
(2) https://www.parkmycloud.com/blog/aws-vs-azure-vs-google-cloud-market-share/ 
(3) https://www.slideshare.net/ivoandreev/azure-machine-learning-and-ml-on-premises
(4) https://www.youtube.com/watch?v=KXkBZCe699A 
(5) https://medium.com/kontikilabs/comparing-machine-learning-ml-services-from-various-cloud-ml-service-providers-63c8a2626cb6 


