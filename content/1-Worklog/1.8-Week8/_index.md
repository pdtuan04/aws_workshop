---
title: "Week 8 Worklog"
date: 2026-06-11
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Complete the overall AWS architecture diagram for the EngExam system.
* Develop a custom exam creation feature based on the user's history of incorrect answers.
* Research and upgrade the CI/CD pipeline from using manual SSH to applying AWS CodeDeploy and Docker Hub.

### Tasks to be implemented this week:

| Day | Task | Start Date | End Date | Resources |
| --- | --- | --- | --- | --- |
| Fri | - **Practice:** AWS Architecture Design.<br>&emsp;+ Design and complete the overall AWS architecture flow for the EngExam system.<br>&emsp;+ Identify components and draw an architecture diagram showing how services interact (VPC, EC2, RDS, S3, ALB, ASG, etc.). | 05/06/2026 | 05/06/2026 | <https://youtu.be/l8isyDe-GwY> |
| Sat | - Learn the theory of the AWS CodeDeploy service.<br> - Research CodeDeploy's automated application deployment mechanism when a new code version is pushed to the repository. | 06/06/2026 | 06/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html> |
| Sun | - **Practice:** Exam Feature (Part 1).<br>&emsp;+ Analyze the logic and retrieve data for questions the user frequently answers incorrectly from their test history. | 07/06/2026 | 07/06/2026 | |
| Mon | - **Practice:** Exam Feature (Part 2).<br>&emsp;+ Build the complete API to automatically generate review exams based on the user's incorrect/failed questions. | 08/06/2026 | 08/06/2026 | |
| Tue | - **Practice:** CI/CD Upgrade (Part 1).<br>&emsp;+ Reconfigure the pipeline flow (GitHub Actions) to automatically build the ASP.NET Core application.<br>&emsp;+ Integrate automatic pushing of the Docker image to Docker Hub. | 09/06/2026 | 09/06/2026 | <https://docs.docker.com/build/ci/github-actions/> |
| Wed | - **Practice:** CI/CD Upgrade (Part 2).<br>&emsp;+ Integrate AWS CodeDeploy into the CI/CD pipeline.<br>&emsp;+ Eliminate the simple SSH method, set up a script (AppSpec) for CodeDeploy to automatically pull the latest image and update the application on EC2. | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file.html> |
| Thu | - **Practice:** System Testing.<br>&emsp;+ Test the new CI/CD flow from the code push step to when the application is automatically deployed successfully.<br>&emsp;+ Verify the accuracy of the exam generation function from incorrect questions. | 11/06/2026 | 11/06/2026 |  |

### Week 8 Achievements:

* Completed and systematized the entire AWS infrastructure architecture flow through a clear and visual architecture diagram.
* Successfully built a smart learning feature: automatically generating review exams from questions users frequently get wrong, helping to optimize the learning experience on the EngExam system.
* Grasped the operating mechanism of AWS CodeDeploy.
* Successfully upgraded the CI/CD pipeline: automated the build process, stored images on Docker Hub, and deployed the application smoothly via CodeDeploy, completely replacing the previous manual SSH operation.