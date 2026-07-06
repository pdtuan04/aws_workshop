# Optimizing Network Architecture with Amazon VPC Regional NAT Gateway

Previously, to ensure high availability, systems required creating separate NAT Gateways in public subnets for each Availability Zone (AZ). With the Regional NAT Gateway (RNAT) mode, AWS allows you to create a single NAT Gateway that operates at the entire Virtual Private Cloud (VPC) level. This system automatically scales out or in across AZs based on actual workloads, helping to simplify network architecture and reduce management overhead.

## 1. Core Benefits

* Better network security: Organizations no longer need to create public subnets to host NAT Gateways. This completely eliminates the risk of accidentally deploying sensitive resources into public subnets and exposing them to the internet.
* Automatic port exhaustion prevention: Each RNAT IP address supports up to 55,000 simultaneous connections to the same destination. With 2 scaling mechanisms:
  * Automatic scale-out mechanism: When the number of connections exceeds the threshold of about 40,000, RNAT automatically adds new IPs within 5 minutes (up to 32 IPs per AZ).
  * Automatic scale-in mechanism: When the number of connections drops below 20,000 and remains there for about 1 hour, the system automatically revokes the IP to save costs.
* VPC IPAM integration: RNAT automatically retrieves IPs from IPAM pools that comply with organizational policies when needing to expand to a new AZ or when load increases.
* Flexible control: Users can choose Automatic mode (AWS handles IP and AZ management) or Manual mode (users allocate Elastic IPs and select AZs themselves). Note in manual mode: if data is generated in an AZ that does not have RNAT enabled, traffic will randomly route to another AZ that has RNAT, which may incur cross-AZ transfer fees.

## 2. Routing and Monitoring

* Flexible routing: RNAT comes with a default Route Table pointing to the Internet Gateway (IGW). This structure allows for the easy insertion of security inspection devices (like Firewalls) into the data flow.
* Comprehensive monitoring: Supports monitoring via Amazon CloudWatch with metrics such as: resource ID, AZ ID, source/destination IP, source/destination Port, and protocol.

## 3. Common Deployment Models

* VPC to Internet (Simplest): Traffic from internal subnets goes straight to RNAT, then to the Internet Gateway (IGW), and out to the network.
* VPC to Internet with traffic inspection: Traffic from internal subnets is first routed through a Firewall (AWS Network Firewall or third-party appliance) for security inspection, then transmitted to RNAT and out to the Internet.

## 4. Important Considerations

* Application scope: RNAT is attached to the entire VPC, not bound to individual subnets. The Route Table of the RNAT cannot be associated with subnets or other RNATs.
* AZ scaling time: In automatic mode, if you deploy resources in a new AZ, RNAT will take an average of 15 - 20 minutes (up to 60 minutes) to expand to that AZ.
* Resource limits: Each VPC can configure a maximum of 5 RNATs.
* Performance: Bandwidth supports from 5 Gbps and can automatically scale up to 100 Gbps per AZ (supporting TCP, UDP, ICMP protocols).
* Current limitations: RNAT currently does not support fully private connectivity. For this requirement, AWS recommends still using the legacy Zonal NAT Gateway.

<br>Group Post Link: <https://www.facebook.com/groups/660548818043427/user/100025022862424>

> Reference: [Introducing Amazon VPC Regional NAT Gateway](https://aws.amazon.com/blogs/networking-and-content-delivery/introducing-amazon-vpc-regional-nat-gateway/)