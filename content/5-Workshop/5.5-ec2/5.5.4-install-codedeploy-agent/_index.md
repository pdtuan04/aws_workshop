---
title : "Install AWS CodeDeploy Agent"
date : 2026-07-01
weight : 4
chapter : false
pre : " <b> 5.5.4 </b> "
---
In this section, we will run the following commands to install the CodeDeploy agent.
```bash
sudo yum update

sudo yum install ruby

sudo yum install wget

sudo cd /home/ssm-user

sudo curl -O [https://aws-codedeploy-ap-southeast-1.s3.ap-southeast-1.amazonaws.com/latest/install](https://aws-codedeploy-ap-southeast-1.s3.ap-southeast-1.amazonaws.com/latest/install)

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
After executing the installation commands, the CodeDeploy agent has been successfully installed.