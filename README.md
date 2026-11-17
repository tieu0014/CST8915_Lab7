# CST8915 Lab 7: Full-stack Cloud-native Development: Introduction to Kubernetes Basics

**Student Name**: Eric Tieu<br>
**Student ID**: 041273376<br>
**Course**: CST8915 Full-stack Cloud-native Development<br>
**Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/w_yjShalB4s)

---
## RabbitMQ
### Stateless
The RabbitMQ service is stateless. It does not store data of queue items once they have been processed.
### No Persistent Storage
With no persistent storage if the RabbitMQ service goes down all queue items in that instance will be lost as well.
### Result of Pod Deletion
As seen in the demo video after the deletion of the RabbitMQ pod a new instance is created. As a result all of the previous data, queue items are also deleted with the original instance and the new instance contains no queue items.
### Solution
To solve the issue of data being lost along with the service going down we can implement a way to store queue items before it is processed by another service.
### Azure Service Bus
According to Azure's documentation Azure Service Bus will hold queue items with redundancies, it also mentions it keeps it in memory or storage until the client reports them as accepted. So if the service goes down it can self heal with the queue items intact.
