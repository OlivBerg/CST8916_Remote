# Assignment 2: Cloud Service Providers Comparison Report

## Executive Summary (10%)

### Summary

This report presents a comparative analysis of the three major cloud computing providers: Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP) are evaluated for their capabilities across modern architectural patterns, including RESTful APIs, GraphQL, WebSocket communications, Data Streaming, and Stream Analysis. This report assesses which provider offers the most robust solutions for real-time applications such as chat services, gaming, and financial trading by reviewing their service catalogues and documentation.

While all three providers offer functional solutions for these technologies, they cater to different organizational needs. AWS is the market leader with the deepest service catalogue, making it a versatile choice for companies of all sizes, from startups to enterprises. Microsoft Azure stands out through its superior enterprise integration and strict compliance standards, making it the optimal choice for large-scale organizations and government entities, particularly for real-time communication needs. GCP, while strong in analytics, relies more heavily on partnered integrations and presents a more fragmented user experience.

### Key Findings and Recommendations:

- Market Position: AWS leads in versatility and maturity, but Azure is the top contender for enterprise-grade security and compliance.

- Service Parity: AWS and Azure are functionally very similar across API and streaming services.

- User Experience: GCP lacks the centralized service hub found in competitors, making navigation more difficult.

- Recommendation: For organizations prioritizing deep compliance frameworks and existing Microsoft integration, Azure is recommended. For those seeking maximum platform maturity and community support, AWS remains the standard.

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

|                    | **Amazon API Gateway** (AWS, n.d.-a) | **Azure API Management** (Microsoft, n.d.-a) | **Apigee API Management** (Apigee API Management, n.d.) |
| :----------------- | :----------------------------------- | :------------------------------------------- | :------------------------------------------------------ |
| **Type**           | Fully Managed API Gateway            | Fully Managed API Gateway                    | Fully Managed API Gateway                               |
| **Data Interface** | REST, WebSocket                      | REST, WebSocket, & GraphQL                   | REST, SOAP, & GraphQL                                   |

### GraphQL Services

|                    | **AWS AppSync** (AWS, n.d.-b) | **Azure API Management** (Microsoft, n.d.-a) | **Apigee API Management** (Apigee API Management, n.d.) |
| :----------------- | :---------------------------- | :------------------------------------------- | :------------------------------------------------------ |
| **Type**           | \*\*Managed GraphQL Service   | Fully Managed API Gateway                    | Fully Managed API Gateway                               |
| **Data Interface** | \*\*GraphQL                   | REST, WebSocket, & GraphQL                   | REST, SOAP, & GraphQL                                   |

### WebSocket Services

|                               | **Amazon API Gateway** (AWS, n.d.-a)                                    | **Azure Web PubSub** (‌Azure Web PubSub – WebSocket Web Publishing, n.d.) | **Apigee API Management** (Apigee API Management, n.d.)                 |
| :---------------------------- | :---------------------------------------------------------------------- | :------------------------------------------------------------------------ | :---------------------------------------------------------------------- |
| **Type**                      | \*\*Managed GraphQL Service                                             | Fully Managed API Gateway                                                 | Fully Managed API Gateway                                               |
| **How it Handles WebSockets** | It acts as a managed service that sits between clients and your server. | It acts as a managed service that sits between clients and your server.   | It acts as a managed service that sits between clients and your server. |

### Data Streaming Services

|                       | **AWS**                                                                                                | **Azure**                                  | **GCP** (Dataflow overview, 2025) |
| :-------------------- | :----------------------------------------------------------------------------------------------------- | :----------------------------------------- | :-------------------------------- |
| **Stream Processing** | Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Stream Analytics (sidramadoss, 2024) | Dataflow                          |
| **Data Ingestion**    | Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Event Hubs (Microsoft, n.d.-b)       | Dataflow                          |

### Stream Analytics

|                      | **AWS**                                                                                                | **Azure**                                  | **GCP**                            |
| :------------------- | :----------------------------------------------------------------------------------------------------- | :----------------------------------------- | :--------------------------------- |
| **Stream Analytics** | Amazon Kinesis Data Streams (What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams, n.d.) | Azure Stream Analytics (sidramadoss, 2024) | Dataflow (Dataflow overview, 2025) |

### Use Case Analysis

Based on the documentation I’ve reviewed, the most common use case is real-time chat, live video games, and financial services like stock exchanges. These tasks are well-suited for both platforms, but I argue Azure is the better overall choice for real-time communication. AWS is a good second option as it supports an enterprise ecosystem, but Azure/Microsoft has a reputation for compliance and security. The size of the company using a cloud service is the key factor. AWS may attract medium-large companies, while Azure may attract large companies and government institutions, making it a more prominent player.

In my opinion, AWS and Azure are quite close competitors and offer very similar features. GCP, on the other hand, relies heavily on partnered services to fill in the gaps. Additionally, GCP was quite difficult to navigate due to the lack of a centralized hub for all its services.

## Conclusion

Overall, the top three giants offer a comprehensive suite of services that convey to user needs ranging from basic RESTful systems to Stream Analytics. While all three providers possess the technical capability to handle core modern architectures like WebSockets and GraphQL, the choice of platform largely depends on organizational scale and ecosystem alignment.

Azure emerges as the preferred choice for large-scale enterprises and government institutions, as highlighted in the analysis. This is due to its superior reputation in compliance, security, and seamless integration with existing Microsoft software. AWS remains a close competitor and market leader, offering a highly mature platform that is versatile enough for large organizations.

In contrast, Google Cloud Platform offers specialized strengths in data handling. However, it currently faces challenges regarding user experience and service centralization compared to its competitors. Ultimately, the decision rests on whether an organization prioritizes the extensive service depth of AWS or the enterprise-ready compliance and real-time communication strengths of Azure.

## AI discloser

I used the ProofRead WritingTool function on Mac to correct my grammar and sentence structures and used Gemini to create table for me, using data that I researched.

## References

API Gateway use cases - Amazon API Gateway. (2025). Amazon.com. https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-overview-developer-experience.html#api-gateway-overview-websocket

Apigee API Management. (n.d.). Google Cloud. https://cloud.google.com/apigee?hl=en

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

Using WebSockets. (2025). Google Cloud Documentation. https://docs.cloud.google.com/apigee/docs/api-platform/develop/websocket-config
‌
What Is Amazon Kinesis Data Streams? - Amazon Kinesis Data Streams. (n.d.). Docs.aws.amazon.com. https://docs.aws.amazon.com/streams/latest/dev/introduction.html

yjin81. (n.d.). What is Azure Web PubSub service? Learn.microsoft.com. https://learn.microsoft.com/en-us/azure/azure-web-pubsub/overview
