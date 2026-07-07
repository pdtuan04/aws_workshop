---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---


# Report on "AWS First Cloud AI Journey Community Day 2026"

### Event Purpose
Participating in the community gathering to connect with Cloud experts, discover new applications of Cloud & Generative AI, experience practical demos, and expand networking within the technology ecosystem.

### Speaker List

- VY LAM - Senior Business Systems Analyst (VPBank)
- THAO NGUYEN - GenAI Engineer (VIB)
- MAI NGUYEN - GenAI Engineer (VIB)
- UYEN LE - GenAI Engineer (VIB)
- ANH PHAM - Cloud Consultant (G-AsiaPacific Vietnam)
- THINH NGUYEN - Devops Engineer (FCAJ)
- TINH TRUONG - Platform Engineer (GoTymeX)
- DUC DAO - Solutions Architect (Cloud Kinetics)
### Highlighted Content

#### How Context Affects the Quality of AI Responses

- How to provide the right context to get higher quality results.
- Do not repeat things that are already pre-fed into the AI, which wastes more resources.
- Avoid irrelevant, redundant contexts, or vague prompts.
- Only provide what is relevant and avoid mixing in another field.
 
#### AI Solutions Supporting Enterprise Operations

- Introduced Amazon Quick Suite as AWS's unified AI solution for enterprises.
- Demo application showing how to automate tasks.

#### CloudFront as Your Foundation

- CloudFront introduced a fixed pricing model instead of the previous pay-as-you-go model to eliminate the risk of bill spikes.
- Practical use cases that customers often care about, such as incurred costs.
- Main customer segments (small website owners, enterprises, medium or high-end enterprises).
- Discussed what CloudFront provides regarding product security.
- Enhanced performance using HTTP/3, data compression, and multi-tier cache architecture.
- Cost optimization via Data Transfer Out and by reducing CPU load for EC2 by using CF to handle TCP handshake and TLS (HTTPS) handshake. This frees EC2 from bearing too much load. The reduction figure given can be from 5% down to 1%.
- Supports custom error pages configuration to provide a more user-friendly experience when the Origin server is unavailable.
#### Sharing the 36-hour journey from idea to a real product

- Shared the journey of participating in LotusHacks to build the UTMorpho product in 36 hours.
- UTMorpho solves the problem where AI-generated interfaces cannot be edited directly and easily suffer from design drift.
- The 36-hour development process focused on rapid role division, building the core, and cutting features.
- Shared the architecture used from user prompt passing through 3 AIs and then saving results to S3.
- Focused on the main features of the application first, rather than trying to have as many features as possible.
- Demoed the product achieved on the competition day.
#### Determinism in Large Language Models

- Setting "deterministic" (temp=0) does not guarantee LLM results are always consistent.
- This phenomenon is due to GPU architecture (floating-point arithmetic) and inference optimization.
- Researchers found no model is fully consistent, and accuracy can vary significantly.
- Use multiple runs and majority voting to increase determinism, or force a structured format.
- Applications should be designed for variation, and trying temp=0.1 can prevent the model from repeating itself.

#### Enterprise-Grade Multi-Agent System
- Cases when working at banks.
- Provided a better solution for credit assessment.
- The system helps optimize costs and time compared to traditional startup credit assessment processes.
### Key Takeaways

- Grasped the importance of constructing appropriate context when using AI to improve the quality of results.
- Understood more about how to optimize performance, cost, and security for applications through Amazon CloudFront with Free Tier.
- Learned the product development process within a short timeframe, from idea to deployment and product demonstration.

### Professional Applications

- Apply knowledge of Amazon CloudFront into the internship project to accelerate access speed, optimize performance, and integrate AWS WAF to enhance security.
- Use AI more effectively in the learning and programming process by constructing appropriate prompts and providing proper context.
- Reference practical experiences of deploying real systems.

### Experience during the event

#### Learning from highly specialized speakers

The event brought many practical perspectives from speakers working at enterprises and technology organizations. The insights did not just focus on technical knowledge but also helped me better understand how Cloud and AI technologies are applied to solve real problems in business.

#### Lessons learned

- Always choose the solution that fits actual requirements instead of chasing new technology.
- System design needs to balance performance, cost, and scalability.
- AI is a highly effective supporting tool, but one needs to know how to set the context and verify results before use.
- To grow in the Cloud field, one must continuously update knowledge and learn from practical experiences.

#### Some images and videos when participating in the event
![Security](../../images/4-events/event1.jpg)