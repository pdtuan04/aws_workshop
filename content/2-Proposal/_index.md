---
title: "Proposal"
date: 2026-07-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# English Learning & Exam Platform
## English Learning System Solution Deployed on AWS High Availability Architecture

### 1. Executive Summary
The English learning system is designed to provide a learning platform that combines memorization methods and community interaction. Core features include a smart Flashcard system for vocabulary memorization, a diverse English article library, a practice testing function, and a hierarchical comment system to enhance learner interaction. The system leverages the power of AWS cloud services to ensure High Availability, automatic scaling, and fully automated CI/CD integration.

### 2. Problem Statement
*Current problem:*
Although there are many high-quality English learning platforms on the market today, learners often face fragmentation: they use a separate app for Flashcards (like Quizlet, Anki), and read articles on another website. The lack of a highly cohesive "All-in-one" environment disrupts the learner's focus flow.

*Solution:*
Develop a centralized learning system that fully integrates study features. The system leverages AWS infrastructure with a combination of WAF, CloudFront, and S3 for fast and secure static content delivery. An Application Load Balancer (ALB) combined with an Auto Scaling Group will route traffic to application servers running Docker containers. Data is securely managed within Private Subnets with SQL Server and access is accelerated using ElastiCache (Valkey). The development process is streamlined thanks to a CI/CD pipeline from GitHub Actions to Docker Hub and AWS CodeDeploy.

*Benefits:*
The solution provides a smooth, fast-loading, uninterrupted learning experience thanks to the load balancing and fault tolerance mechanisms. Setting up a systematic infrastructure creates a solid foundation for the graduation internship and practical project development, while effectively controlling costs by utilizing free tiers (CloudFront, WAF) and appropriately sized nodes (t3.micro, t4g.micro).

### 3. Solution Architecture  
The system operates entirely within the secure Amazon VPC network environment spanning multiple Availability Zones to ensure High Availability.

![EngExam Cloud & Deployment Architecture](../images/2-proposal/architechture.drawio.png)

*Data interaction flow:*
1. User sends a request to the system, passing through CloudFront.
2. Through CloudFront, it checks the first AWS WAF rules defense layer to filter out common web attacks.
3. Requests for static resources are processed directly by CloudFront and offloaded via an Amazon S3 Bucket.
4. Dynamic requests (APIs) are routed by CloudFront through the Internet Gateway (IG) to enter the VPC.
5. The traffic flow goes to the Application Load Balancer (ALB) for load distribution.
6. The ALB evenly distributes traffic to EC2 servers located within the Auto Scaling Group in the Private Subnets.
7. The EC2 Instances handle business logic and interact with the Amazon RDS (SQL Server) database configured as a Primary DB and Standby DB cluster for automatic failover during incidents.
8. Frequently queried data or exam configurations are distributed and cached directly at Amazon ElastiCache (Valkey) Replica Node & Primary Node to reduce the load on the RDS.
9. When EC2s in the private subnet need to download libraries or connect to the Internet (send emails, connect to Docker Hub), outbound traffic goes through a centralized Regional NAT Gateway to optimize costs.
10. From the Regional NAT Gateway, traffic goes out through the Internet Gateway.
11. Amazon CloudWatch continuously monitors performance metrics (CPU, Network) of the EC2 instances.
12. When the system load exceeds the configured threshold, CloudWatch triggers an Alarm.
13. The Alarm issues a Trigger Scaling command requesting the Auto Scaling Group to automatically add servers (Scale-out).
14. Simultaneously, a Send Notifications alert is routed to Amazon SNS to automatically send a warning email to the administrator when a new instance is initialized.

*CI/CD Automation Flow:*

15. The Developer commits and Pushes Code to the GitHub Repository.
16. The push code action automatically triggers GitHub Actions Workflows to run the testing process and Build Code To Image.
17. The successfully built Docker image is Pushed to the Docker Hub repository.
18. The pipeline compresses the deployment configuration source code into a Publish Deploy Artifact.
19. This Zip File is directly pushed to a temporary Amazon S3 Bucket for deployment.
20. GitHub Actions calls the AWS CodeDeploy service to notify it of the new version.
21. The AWS CodeDeploy Agent on the servers accesses S3 to Get Files containing the artifact.
22. CodeDeploy executes the deployment script.
23. Commands all EC2s to pull the latest image from Docker Hub.

### 4. Technical Implementation

*Deployment Phases*
The project is carried out throughout the internship, divided into 3 main phases to ensure progress from grasping the technology to system completion:
1. Research and familiarize with core services (Month 1): Focus on researching theory and practicing basic lab exercises on AWS. The goal of this phase is to get accustomed to the operations and understand the working mechanisms of core infrastructure services (such as VPC, EC2, RDS, S3).
2. Define architecture and calculate costs (Early Month 2): Sketch and draw the overall system architecture diagram. Create an infrastructure cost estimation table (using AWS Pricing Calculator), thereby making decisions to adjust services and architecture to optimize the operational budget.
3. Develop and integrate the system (Mid-Month 2 - Early Month 3): Start the actual building process. Program the core features (Backend & Frontend) and gradually integrate and deploy advanced services (Auto Scaling, ALB, ElastiCache, CI/CD, RabbitMQ, WAF) to the Cloud environment.
4. Test and finalize (Late Month 3): Review the entire project. Conduct functional testing and completely resolve any arising bugs. Package the environment and complete the final report documents.

*Technical Requirements*
* Cloud Infrastructure (AWS): Requires knowledge of VPC network configuration (Public/Private Subnet, Internet Gateway, Regional NAT Gateway). Ability to set up an EC2 server cluster operating under an Auto Scaling Group and ALB. Use Amazon S3 combined with CloudFront to distribute static content, integrating the AWS WAF security shield. Store data with RDS (SQL Server) and set up the ElastiCache (Valkey) cache.
* Architecture & Backend (.NET): Use C# ASP.NET Core, Entity Framework Core. Grasp the CQRS architecture design mindset to separate Read/Write flows. Use a Message Broker (installing RabbitMQ and MassTransit) to handle event-driven operations and distributed data synchronization.
* CI/CD & Automation: Use Container virtualization technology (Docker, Docker Compose). Ability to write automation scripts (Pipelines) using GitHub Actions to build images, push them to Docker Hub, and configure AppSpec for AWS CodeDeploy to perform In-Place Deployment.
* Frontend: UI development skills using React, ensuring a smooth experience for main operational flows such as taking multiple-choice tests, flipping flashcards, and interacting via comments.

### 5. Roadmap & Milestones

The project is planned for deployment entirely within a 3-month internship with the following milestones:

* Month 1: Kick-off and Platform Familiarization:
  * Research theory and practice lab exercises for basic AWS services (VPC, EC2, RDS, S3).
  * Review development technologies (ASP.NET Core, React) and Docker.

* Month 2: Architectural Design and Initial Building
  * *Early month:* Sketch the overall architectural diagram, calculate, and optimize infrastructure costs.
  * *Mid - Late month:* Build core features (applying CQRS). Integrate infrastructure into the Cloud environment (ALB, Auto Scaling) and set up basic CI/CD.

* Month 3: Optimization, Testing, and Packaging
  * Finalize the CI/CD pipeline (AWS CodeDeploy), data synchronization (RabbitMQ), Cache configuration (Valkey), and security (WAF).
  * Comprehensive testing and load testing evaluation (JMeter).
  * Thoroughly fix bugs, record a demo video, and complete final report documents.

### 6. Budget Estimation

*Infrastructure Costs*
- Amazon EC2: 9.42 USD/month (1 t3.small Instance applying 3-year Compute Savings Plans, No Upfront).
- Amazon RDS: 22.63 USD/month (1 db.t3.micro Instance, SQL Server Express Edition with free license).
- Amazon ElastiCache: 14.02 USD/month (1 cache.t4g.micro Node, Valkey engine on On-Demand).
- Amazon S3 Standard: 0.25 USD/month (Estimated storage of 10 GB of static resources at 0.025 USD/GB).
- Amazon CloudFront & AWS WAF: 0.00 USD/month (Free Tier package including WAF supporting 5 rules, 1 million requests, 100 GB data).
- AWS CodeDeploy: 0.00 USD/month (Completely free when deploying source code to EC2/Auto Scaling Group).
- Amazon CloudWatch: 0.00 USD/month (Basic EC2 performance monitoring included in Free Tier).
- Amazon SNS: 0.00 USD/month (Automatic warning emails included in Free Tier).
- Docker Hub: 0.00 USD/month (Free Tier account for Public Repository).

*Total*: 46.32 USD/month, 555.84 USD/12 months.

### 7. Risk Assessment
*Risk Matrix*
- Security misconfiguration (Security Groups/VPC): High impact, medium probability.
- Deployment failure (Downtime during updates): High impact.
- Unexpected costs (Especially NAT Gateway and Data Transfer): Medium impact, medium probability.

*Mitigation Strategy*
- Only open necessary ports, place all DBs, ElastiCache, and processing EC2s into Private Subnets.
- Configure Amazon CloudFront to force all traffic from HTTP to HTTPS (Redirect HTTP to HTTPS).
- Set up AWS Budgets and CloudWatch Billing Alarms to warn immediately if costs exceed the allowable threshold.

### 8. Expected Outcomes
- Technical: Successfully build a stable English learning system that is fault-tolerant thanks to Multi-AZ and scales automatically based on traffic. The deployment process is fully automated right from code push.
- Product: Users have a smooth platform to practice vocabulary via Flashcards, take English tests, read articles, and exchange academic knowledge through a hierarchical comment system.