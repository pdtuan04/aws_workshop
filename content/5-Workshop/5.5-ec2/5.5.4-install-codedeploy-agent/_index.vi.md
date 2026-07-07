---
title : "Cài đặt AWS CodeDeploy Agent"
date : 2026-07-01
weight : 4
chapter : false
pre : " <b> 5.5.4 </b> "
---
Phần này mình sẽ chạy các câu lệnh sau để cài đặt CodeDeploy agent.
```
sudo yum update

sudo yum install ruby

sudo yum install wget

sudo cd /home/ssm-user

sudo curl -O https://aws-codedeploy-ap-southeast-1.s3.ap-southeast-1.amazonaws.com/latest/install

sudo chmod +x ./install

sudo ./install auto

systemctl status codedeploy-agent

sudo systemctl stop codedeploy-agent

sudo rm -rf /opt/codedeploy-agent/.appprop

#!/bin/bash

sudo systemctl restart chronyd
sudo chronyc makestep

sudo dnf reinstall ca-certificates -y
sudo update-ca-trust

sudo systemctl restart codedeploy-agent

```
![overview](../../../images/5-Workshop/5.5-ec2/59.png)
Sau khi chạy xong các câu lệnh cài đặt mình đã có CodeDeploy agent.