
class: center, middle

# Aurora Serverless & Event Streaming as the source of truth

#### Bof 12/01/2017 - Nicolas Guignard

.octo-logo[![octo logo](./img/octo-logo.png)]

---


class: center, middle, title1bg

# Aurora Serverless

---
class: center, middle

## What is Aurora ?

Relational Database 

Fully managed by AWS RDS 

???

1
 - Relational database on the cloud which compares to opensource dbs like MySQL and Postgres
2
 - automates time-consuming administration tasks like hardware provisioning, database setup, patching, and backups

---

class: center, middle

## Serverless ?

???
on-demand auto-scaling configuration for Aurora where the database will automatically start-up, shut down, and scale up or down capacity based on your application's needs.
a simple, cost-effective option for infrequent, intermittent, or unpredictable workloads
pay on a per-second basis for the database capacity you use when the database is active

---
class: center, middle

## Use cases

New application

Variable workloads

Infrequent used applications

Dev / UAT DBs

???

Problem:
1
 - unknown needed capacity
2
 - Applications with peak of activity that cannot be predicted


---

class: center, middle, title2bg

# Event Streaming as the source of truth

???

event streaming has its benefits over traditional message queuing
event streaming can be used with platforms like Kafka or kinesis Stream
A service with an Event Sourcing design can use Kafka as its event store then those events will be  available for other services to consume

---

class: center, middle

## Events are truth

Manage async

Bring together different services

Never forget 

???
Events are facts that follow each other and it tells a story
if persisted / kept somewhere it gives an history
Version control our data : always recoverable or auditable and gives the possibility to rewind

---

class: center, middle

## Event sourcing should have one source of truth

???
having a database as well as a event platform would require maintaining consistency between two data models that would probably be different. 
Database objects are often mutables while it is not the case for events
No dual-write
merge both models
