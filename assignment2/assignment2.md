# Assignment 2: Cloud Service Providers Comparison Report

## Executive Summary (10%)

Brief overview of the comparison (200-300 words)
Key findings and recommendations

## Introduction

The goal of this report is to compare and contrast key similarities and differences between major cloud services. This comparison will highlight services used for RESTful API, GraphQL, WebSocket, Data Streaming and Stream Analysis. The major cloud providers used in this report will be Azure, AWS and GCP.

### Microsoft Azure

Launched in 2010 commercially, Azure is the second-largest provider. It is tightly integrated with Microsoft’s ecosystem is ideal for organizations invested in Microsoft software, offering enterprise integration, hybrid cloud support, and strong compliance certifications. (Abandy, 2022) (Perry, n.d.)

### Amazon Wev Services (AWS)

AWS, launched in 2006, is the market leader with the largest market share and most extensive service catalogue. It excels in market dominance, service depth, and community support, making it ideal for startups, enterprises, and organizations prioritizing platform maturity. (Our Origin, n.d.) (Perry, n.d.)

### GCP

GCP, launched in 2008, is the third-largest cloud provider. It excels in data analytics, machine learning, and containerization, making it ideal for companies focused on these areas. (Stevens, 2017)(Perry, n.d.)

## Service Comparison

### RESTful API Services 

|  | **Amazon API Gateway** (AWS, n.d.-a) | **Azure API Management** (Microsoft, n.d.-a) | **Apigee API Management** (Google Cloud, n.d.) |
| :--- | :--- | :--- | :--- |
| **Type** | Fully Managed API Gateway | Fully Managed API Gateway | Fully Managed API Gateway|
| **Data Interface** | REST, WebSocket | REST, WebSocket, & GraphQL  | REST, SOAP, & GraphQL  |


### GraphQL Services

| | **AWS AppSync** (AWS, n.d.-b) | **Azure API Management** (Microsoft, n.d.-a) | **Apigee API Management** (Google Cloud, n.d.) |
| :--- | :--- | :--- | :--- |
| **Type** | **Managed GraphQL Service | Fully Managed API Gateway | Fully Managed API Gateway |
| **Data Interface** | **GraphQL | REST, WebSocket, & GraphQL  | REST, SOAP, & GraphQL |



### WebSocket Services


|  | **Amazon API Gateway** (AWS, n.d.-a)| **Azure Web PubSub** (‌Azure Web PubSub – WebSocket Web Publishing, n.d.) | **Firebase Realtime Database** (Firebase, 2025) |
| :--- | :--- | :--- | :--- |
| **Type** | **Fully Managed API Gateway** | **Dedicated Real-time Messaging Service** | **Backend-as-a-Service** |
| **How it Handles WebSockets** | It acts as a managed service that sits between clients and your server.| It acts as a managed service that sits between clients and your server. | Clients subscribe to data paths in the DB. When data changes, Firebase automatically pushes the update to all connected clients via WebSockets. |


### Data Streaming Services

| | **AWS**  | **Azure** | **GCP** (Dataflow overview, 2025) |
| :--- | :--- | :--- | :--- |
| **Stream Processing** | Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Stream Analytics (sidramadoss, 2024) | Dataflow |
| **Data Ingestion** |  Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Event Hubs (Microsoft, n.d.-b) | Dataflow |

### Stream Analytics 

|                   | **AWS**              | **Azure**                        | **GCP**            |
| :-------------------------------- | :------------------- | :------------------------------- | :----------------- |
| **Stream Analytics** | Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Stream Analytics (sidramadoss, 2024) | Dataflow (Dataflow overview, 2025)|

### Use Case Analysis 

Present two real-world scenarios for real-time applications
Recommend the most suitable CSP for each with justification
Consider: cost, performance, ease of integration, ecosystem

## Conclusion

Summary of findings and overall recommendations


## AI discloser
I used the ProofRead WritingTool function on Mac to correct my grammar and sentence structures and used Gemini to create table for me using data that I researched.

## References

AWS. (n.d.-a). Amazon API Gateway Features | API Management | Amazon Web Services. Amazon Web Services, Inc. https://aws.amazon.com/api-gateway/features/

AWS. (n.d.-b). Building a real-time WebSocket client in AWS AppSync - AWS AppSync GraphQL. Amazon.com. Retrieved November 22, 2025, from https://docs.aws.amazon.com/appsync/latest/devguide/real-time-websocket-client.html

Azure Web PubSub – WebSocket Web Publishing | Microsoft Azure. (n.d.). Microsoft.com. https://azure.microsoft.com/en-gb/products/web-pubsub

Dataflow overview. (2025, November 12). Google Cloud Documentation. https://docs.cloud.google.com/dataflow/docs/overview

Firebase. (2025, November 20). Firebase Realtime Database. Firebase. https://firebase.google.com/docs/database

Firebase Data Connect. (2025, November 20). Firebase. https://firebase.google.com/docs/data-connect

Microsoft. (n.d.-a). Azure API Management - Overview and key concepts. In Microsoft. https://learn.microsoft.com/en-us/azure/api-management/api-management-key-concepts

Microsoft. (n.d.-b). What is Azure Event Hubs? - a Big Data ingestion service - Azure Event Hubs. Learn.microsoft.com. https://learn.microsoft.com/en-us/azure/event-hubs/event-hubs-about

Our origins. (n.d.). Amazon Web Services, Inc. https://aws.amazon.com/about-aws/our-origins/

Perry, M. (n.d.). AWS vs GCP vs Azure: Which Cloud Platform is Best for your Business - Qovery. Qovery.com. https://www.qovery.com/blog/aws-vs-gcp-vs-azure

Roosevelt_Abandy. (2022, August 24). The History of Microsoft Azure. TECHCOMMUNITY.MICROSOFT.COM. https://techcommunity.microsoft.com/blog/educatordeveloperblog/the-history-of-microsoft-azure/3574204

sidramadoss. (2024, December 17). Introduction to azure stream analytics. Learn.microsoft.com. https://learn.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction

Stevens, B. (2017, March 10). Google Cloud Platform: your Next home in the cloud. Google Cloud Blog; Google Cloud. https://cloud.google.com/blog/products/gcp/google-cloud-platform-your-next-home-in-the-cloud?hl=en
‌
What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams. (n.d.). Docs.aws.amazon.com. https://docs.aws.amazon.com/streams/latest/dev/introduction.html
