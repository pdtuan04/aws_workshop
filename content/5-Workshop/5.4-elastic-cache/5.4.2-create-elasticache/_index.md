---
title : "Create ElastiCache (Valkey)"
date : 2026-07-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---
1. Go to the ElastiCache console and click **Create cache**.
![overview](../../../images/5-Workshop/5.4-elastic-cache/32.png)

2. Configure ElastiCache:
- Engine: Select **Valkey**.
- Deployment option: Select **Node-based cluster**.
- Creation method: Select **Cluster cache**.
- Cluster mode: Select **Disabled**.     
![overview](../../../images/5-Workshop/5.4-elastic-cache/33.png)

3. Enter a name for the cluster.
![overview](../../../images/5-Workshop/5.4-elastic-cache/34.png)

4. For the node type, select **cache.t4g.micro** to save credits.
![overview](../../../images/5-Workshop/5.4-elastic-cache/35.png)

5. Set the number of replicas to **1**.
![overview](../../../images/5-Workshop/5.4-elastic-cache/36.png)

6. Select the subnet group created in the previous step.
![overview](../../../images/5-Workshop/5.4-elastic-cache/37.png)

7. For Availability Zone placements, choose **Specify Availability Zones** and click next.
![overview](../../../images/5-Workshop/5.4-elastic-cache/38.png)

8. Keep the default settings in the Advanced section, click next to review everything, and click **Create**.
![overview](../../../images/5-Workshop/5.4-elastic-cache/39.png)

9. Since the Security Group step was missed during initial creation, modify the newly created ElastiCache cluster:
- Scroll down to the security groups section, select the Security Group previously created for ElastiCache in step 5.2.2, review the changes, and click save. 
![overview](../../../images/5-Workshop/5.4-elastic-cache/40.png)

Following the steps above, the ElastiCache cluster has been successfully created and the primary endpoint is now available.
![overview](../../../images/5-Workshop/5.4-elastic-cache/41.png)