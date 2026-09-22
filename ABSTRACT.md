# Azure Service Bus Topics for Publish-Subscribe Integration

## Abstract

The **Azure Service Bus Topics for Publish-Subscribe Integration** project demonstrates a cloud-based messaging system using **Microsoft Azure Service Bus** and Python. The main objective of the project is to implement a reliable publish-subscribe communication model in which a single producer can publish student event messages and multiple subscribers can receive only the messages relevant to them.

In this system, a Python-based producer collects student information such as **student name, branch, and event type**. The producer publishes these messages to an Azure Service Bus Topic named **`studentevents`**. The topic acts as a central message distribution point and allows the producer and consumers to work independently.

Three subscriptions are created under the topic: **RegistrationSubscription, NotificationSubscription, and AnalyticsSubscription**. SQL-based subscription filters are configured using the `EventType` message property so that Registration events are delivered to the Registration subscription, Notification events are delivered to the Notification subscription, and Analytics events are delivered to the Analytics subscription. This demonstrates how Azure Service Bus can route different types of messages to the appropriate consumers.

Python receiver programs are used to receive and process messages from the subscriptions. After successful processing, messages are completed so that they are removed from the active queue. The project also demonstrates message delivery attempts and **Dead Letter Queue (DLQ)** functionality. Messages that repeatedly fail to be processed can be moved to the dead-letter queue, where they can be inspected for troubleshooting and failure analysis.

The project is verified using **Azure Service Bus Explorer**, which is used to inspect topics, subscriptions, messages, filters, active messages, and dead-letter messages. Overall, the project demonstrates important cloud messaging concepts including **publish-subscribe architecture, message filtering, asynchronous communication, reliable message processing, subscription-based routing, and failure handling** using Azure Service Bus.

## Technologies Used

- Microsoft Azure Service Bus
- Azure Service Bus Topic
- Topic Subscriptions
- SQL Filters
- Dead Letter Queue (DLQ)
- Python
- Google Colab
- Azure Service Bus Explorer
