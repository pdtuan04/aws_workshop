---
title : "Create RDS (SQL Server)"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

1. Click **Create database** to begin setting up the database.
![overview](../../../images/5-Workshop/5.3-rds/18.png)

2. Since our system uses SQL Server, select **Microsoft SQL Server** and choose **Standard create**.
![overview](../../../images/5-Workshop/5.3-rds/19.png)

3. Select the edition.
![overview](../../../images/5-Workshop/5.3-rds/20.png)

4. In the **Credentials management** section, select **Self managed** to set up your own master password.
![overview](../../../images/5-Workshop/5.3-rds/21.png)

5. For the Instance configuration, choose **db.t3.micro** as the instance class.
![overview](../../../images/5-Workshop/5.3-rds/22.png)

6. Set the **Allocated storage** to **20** GiB.
![overview](../../../images/5-Workshop/5.3-rds/23.png)

7. Select your VPC and choose the DB subnet group created in the previous step.
![overview](../../../images/5-Workshop/5.3-rds/24.png)

8. Select the appropriate Security Group for your VPC.
![overview](../../../images/5-Workshop/5.3-rds/25.png)

9. Choose **Standard** authentication method.
![overview](../../../images/5-Workshop/5.3-rds/26.png)

10. Click **Create database** to complete the setup process.
![overview](../../../images/5-Workshop/5.3-rds/27.png)

Following the steps above, the database for the system has been successfully created and the connection endpoint is now available.
![overview](../../../images/5-Workshop/5.3-rds/42.png)