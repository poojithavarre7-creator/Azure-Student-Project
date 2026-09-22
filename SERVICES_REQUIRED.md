# Services Required

## Project Title
**Azure Service Bus Topics for Publish-Subscribe Integration**

## Services and Tools Used

### 1. Azure Service Bus Namespace
Provides the cloud messaging environment for the project and hosts the Service Bus topic.

### 2. Azure Service Bus Topic
A topic named **`studentevents`** is used to publish student event messages from the Python producer.

### 3. Topic Subscriptions
Three subscriptions are created to receive different types of events:

- **RegistrationSubscription** – receives Registration events
- **NotificationSubscription** – receives Notification events
- **AnalyticsSubscription** – receives Analytics events

### 4. Subscription SQL Filters
SQL filters are used to route messages according to the `EventType` property.

- Registration → `EventType = 'Registration'`
- Notification → `EventType = 'Notification'`
- Analytics → `EventType = 'Analytics'`

### 5. Dead Letter Queue (DLQ)
The Dead Letter Queue stores messages that cannot be successfully processed after the configured delivery attempts. It helps in troubleshooting and failure analysis.

### 6. Azure Service Bus Explorer
Used to send, receive, inspect, and monitor messages, subscriptions, active messages, and dead-letter messages.

### 7. Python
Python is used to create the producer and consumer programs and communicate with Azure Service Bus.

### 8. Google Colab
Google Colab is used to execute the Python programs and demonstrate the complete messaging workflow.

## Overall Flow

**Python Producer → Azure Service Bus Topic → Subscription Filters → Registration / Notification / Analytics Consumers → Dead Letter Queue (for failed messages)**

## Main Concepts Demonstrated

- Publish-Subscribe Messaging
- Asynchronous Communication
- Message Filtering
- Multiple Subscriptions
- Message Completion
- Delivery Attempts
- Dead Letter Queue
- Cloud-Based Message Processing
