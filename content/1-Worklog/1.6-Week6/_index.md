---
title: "Week 6 Worklog"
date: 2026-05-28
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Fix outstanding bugs related to exams and S3 file storage.
* Add basic user features: Account management and password reset.
* Build the hierarchical comment feature.
* Learn and apply Message Queue (RabbitMQ) combined with the Outbox Pattern to synchronize data between databases.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - **Practice:** System Bug Fixing.<br>&emsp;+ Fix bugs in the exam creation function.<br>&emsp;+ Resolve errors occurring during file uploads to Amazon S3 to ensure a stable file flow. | 22/05/2026 | 22/05/2026 | |
| Sat | - **Practice:** User Features.<br>&emsp;+ Build the account management API.<br>&emsp;+ Build the password reset feature for users (integrated with the email sending API from last week). | 23/05/2026 | 23/05/2026 | |
| Sun |Day Off| 24/05/2026 | 24/05/2026 |  |
| Mon | - Learn the theory of Message Brokers and RabbitMQ.<br> - Research the MassTransit library in .NET.<br> - Understand how the Outbox Pattern works in solving distributed data synchronization problems. <br> - **Practice:** Database Optimization & Queue Setup.<br>&emsp;+ Analyze and optimize the read database specifically for data reading tasks.<br>&emsp;+ Install RabbitMQ and configure MassTransit in the project. | 25/05/2026 | 25/05/2026 | <https://masstransit.io/documentation/concepts>|
| Tue | - **Practice:** CQRS Data Synchronization.<br>&emsp;+ Configure the Outbox Pattern to safely store events.<br>&emsp;+ Use MassTransit and RabbitMQ to publish/consume messages, synchronizing data from the write database to the read database. <br>&emsp;+ Resynchronize cache data when changes occur. | 26/05/2026 | 26/05/2026 | <https://masstransit.io/documentation/patterns/outbox> |
| Wed | - **Practice:** Comment Feature.<br>&emsp;+ Analyze and design the data table for hierarchical comments.<br>&emsp;+ Build basic APIs (add, edit, delete comments). | 27/05/2026 | 27/05/2026 | |
| Thu | - **Practice:** Comment Feature & Testing.<br>&emsp;+ Complete the query flow to retrieve the hierarchical comment list.<br>&emsp;+ Retest the entire data synchronization flow via RabbitMQ and the newly built features. | 28/05/2026 | 28/05/2026 | |

### Week 6 Achievements:

* Successfully fixed bugs in the exam creation function and AWS S3 file upload, allowing the system to function.
* Completed the account management API and the secure password reset flow via email.
* Learned the basic concepts of Message Brokers (RabbitMQ) and the Outbox Pattern.
* Re-optimized the read database.
* Successfully took initial steps to configure MassTransit and RabbitMQ to synchronize data from the Write Database to the Read Database, minimizing the risk of data loss during system failures.
* Designed and built the data structure and APIs for the hierarchical comment feature.