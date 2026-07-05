---
title: "Week 4 Worklog"
date: 2026-05-14
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Design the database for the system.
* Create the User Interface (UI) for the system.
* Research and apply advanced architecture (CQRS Pattern) in developing core APIs.
* Deploy a secure user authentication system using OAuth2 with Google.
* Optimize application performance using Redis Cache, solving the data consistency problem.
* Take initial steps in approaching the basic CI/CD pipeline.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - **Practice:** Data Design.<br>&emsp;+ Understand potential requirements in the system. <br>&emsp;+ Design the database for the web server system. <br>&emsp;+ Apply the Code-First approach with Entity Framework Core Migrations to initialize and manage database versions. | 08/05/2026 | 08/05/2026 | |
| Sat | - Learn basic UI/UX design principles for an examination/practice system.<br> - **Practice:** Interface Design.<br>&emsp;+ Design the UI for system functions.<br>&emsp;+ Ensure user experience for the main operation flows. | 09/05/2026 | 09/05/2026 | |
| Sun | - Research theory on Grant Types in the OAuth2 standard.<br> - **Practice:** Authentication and Security.<br>&emsp;+ Build user authentication APIs.<br>&emsp;+ Integrate the OAuth2 standard into the system to manage access permissions. | 10/05/2026 | 10/05/2026 | <https://learn.microsoft.com/vi-vn/aspnet/core/security/authentication/social/google-logins?view=aspnetcore-9.0> |
| Mon | - Learn about the CQRS (Command Query Responsibility Segregation) architecture and Read/Write flow separation.<br> - **Practice:** API Development (Part 1).<br>&emsp;+ Apply the CQRS Pattern to design processing flows.<br>&emsp;+ Build APIs for the examination and practice functions. | 11/05/2026 | 11/05/2026 | <https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs> <br> <https://200lab.io/blog/cqrs-la-gi>|
| Tue | - **Practice:** API Development (Part 2).<br>&emsp;+ Continue applying the CQRS Pattern.<br>&emsp;+ Build APIs for post management and resource CRUD flows. | 12/05/2026 | 12/05/2026 | |
| Wed | - Research theory on Caching strategies (Cache-Aside), how to validate data when caching, and methods to minimize errors, ensuring Data Consistency.<br> - **Practice:** Performance Optimization.<br>&emsp;+ Install and use Redis to cache frequently accessed data.<br>&emsp;+ Implement an event-driven mechanism to automatically invalidate (delete) cache when data changes. | 13/05/2026 | 13/05/2026 | <https://learn.microsoft.com/en-us/azure/architecture/patterns/cache-aside> |
| Thu | - Research theory on Continuous Integration and Continuous Deployment (CI/CD).<br> - **Practice:** CI/CD Automation.<br>&emsp;+ Learn and configure a trial CI/CD pipeline with GitHub Actions. | 14/05/2026 | 14/05/2026 | <https://dev.to/mfyz/simple-gitlab-cicd-deployment-via-sshrsync-8b6> |

### Week 4 Achievements:

* Completed the database and UI design, creating a solid foundation for the feature development process.
* Understood and successfully built a secure user authentication mechanism by integrating OAuth2.
* Grasped the mindset and applied the CQRS Pattern in API development (examination, practice, resource management), clearly separating read/write flows and increasing system scalability.
* Understood the nature of Caching and data consistency. Significantly improved API response speed by integrating Redis Cache, while trying my best to thoroughly resolve data discrepancy issues using an event-driven cache invalidation mechanism.
* Grasped the process of automating code testing and deployment through GitHub Actions.