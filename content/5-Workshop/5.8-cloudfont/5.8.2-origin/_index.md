---
title : "Configure Origin and Behavior"
date : 2026-07-01 
weight : 2
chapter : false
pre : " <b> 5.8.2 </b> "
---
1. Go to the Origin of the newly created CloudFront and configure it as shown in the image.
- Click Create.
- For Origin Domain, I choose the ALB I created, set Port to 80, and click Create Origin.
![overview](../../../images/5-Workshop/5.8-cloudfont/161.png)
2. Continue to the Behavior section and configure as shown.
- I set Path to `/images/*`
- Choose the S3 that stores static assets.
- For Viewer protocol policy, I choose HTTP to HTTPS to automatically redirect HTTP requests to HTTPS, ensuring a secure connection.
- Allowed HTTP methods `GET, HEAD`.
![overview](../../../images/5-Workshop/5.8-cloudfont/163.png)
3. I keep the lower section as default and create.
![overview](../../../images/5-Workshop/5.8-cloudfont/162.png)
4. I continue adding the next Behavior.
- For Origin and origin groups, I choose the ALB.
- For Viewer protocol policy, I also choose HTTP to HTTPS to automatically redirect HTTP requests to HTTPS.
- Allowed HTTP methods `GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE`.
![overview](../../../images/5-Workshop/5.8-cloudfont/164.png)
5. I set Cache policy to CachingDisable and create, then it's done.
![overview](../../../images/5-Workshop/5.8-cloudfont/166.png)