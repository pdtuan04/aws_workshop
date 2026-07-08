---
title: "Week 7 Worklog"
date: 2026-06-04
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Design the database and fully build the exam history feature (Backend & UI).
* Learn about and deploy the Application Load Balancer (ALB) combined with Auto Scaling solutions on AWS.
* Perform load testing on the system using Apache JMeter to verify auto-scaling capabilities.
* Set up an automated email notification system using Amazon SNS.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - **Practice:** Data Design.<br>&emsp;+ Analyze potential requirements for the history feature in the system.<br>&emsp;+ Design the user exam history table. | 29/05/2026 | 29/05/2026 | |
| Sat | - **Practice:** Backend Development.<br>&emsp;+ Build the API to save the exam history after the user completes it.<br>&emsp;+ Build the API to retrieve the user's exam history list. | 30/05/2026 | 30/05/2026 | |
| Sun |Day Off| 31/05/2026 | 31/05/2026 | |
| Mon | - **Practice:** Frontend Development.<br>&emsp;+ Build the User Interface (UI) to display the exam history section for users. <br> - **Practice:** ALB & Auto Scaling Deployment (Part 1).<br>&emsp;+ Configure the Application Load Balancer to connect with the Auto Scaling Group.<br>&emsp;+ Deploy Manual Scaling (add servers manually) and Scheduled Scaling (set a schedule to automatically add servers). | 01/06/2026 | 01/06/2026 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> <br> <https://000006.awsstudygroup.com/>|
| Tue | - **Practice:** Auto Scaling Deployment (Part 2) & Alerts.<br>&emsp;+ Deploy Dynamic Scaling (automatically scale based on actual system load).<br>&emsp;+ Configure the automated email notification function using Amazon SNS when a new server is initialized. | 02/06/2026 | 02/06/2026 | <https://docs.aws.amazon.com/sns/latest/dg/welcome.html> <br> <https://000006.awsstudygroup.com/>|
| Wed | - **Practice:** Test Preparation.<br>&emsp;+ Install the Apache JMeter tool.<br>&emsp;+ Build a Test Plan simulating a large volume of requests sent to the system. | 03/06/2026 | 03/06/2026 | <https://jmeter.apache.org/usermanual/get-started.html> |
| Thu | - **Practice:** Actual System Testing.<br>&emsp;+ Run JMeter to conduct load testing for the configured Auto Scaling solution.<br>&emsp;+ Monitor the server initialization process on AWS and confirm the email notifications from SNS. | 04/06/2026 | 04/06/2026 | |

### Week 7 Achievements:

* Completed the database design, APIs, and UI for the exam history feature, allowing users to review their results.
* Successfully configured the Application Load Balancer (ALB) combined with 3 Auto Scaling strategies: Manual, Scheduled, and Dynamic.
* Installed and applied basic JMeter to simulate load, thereby successfully verifying the auto-scaling (scale-out) capability of the system.
* Successfully integrated the Amazon SNS service, ensuring the system automatically sends email notifications whenever a new EC2 instance is created during the scaling process.