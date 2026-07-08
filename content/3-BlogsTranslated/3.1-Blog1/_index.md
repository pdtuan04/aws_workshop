---
title: "Blog 1"
date: 2026-07-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Benefits of Combining Amazon CloudFront with Application Load Balancer

As applications increasingly serve users across different geographical regions, ensuring access speed, high availability, and reasonable operational costs becomes a crucial requirement. One of the architectures recommended by AWS is combining Amazon CloudFront with an Application Load Balancer (ALB).

Instead of having users access the ALB directly, CloudFront acts as a global access point through a network of hundreds of edge locations. This architecture brings many benefits in terms of performance, security, and cost optimization, while still ensuring scalability for systems serving a global user base.

## 1. Improving Access Performance

In a traditional model, all user requests are sent directly to an ALB located in an AWS Region. This can increase latency for users located far from the deployment region.

When using CloudFront, static content like images, CSS, and JavaScript is cached at the edge locations closest to the users, significantly reducing response times. For dynamic content, CloudFront maintains persistent TCP connections with the ALB, reducing the overhead of re-establishing TCP/TLS connections for each request and improving response speeds.

According to AWS test results:
* Time-To-First-Byte (TTFB) is improved by about 15–25% for users in the same region as the origin.
* For intercontinental access, the improvement reaches about 35–50%.

As a result, users can receive faster responses, especially when accessing from geographical locations far from the deployment infrastructure.

## 2. Enhancing Security
![Security](../../images/3-BlogsTranslated/cfblog.png)

Placing CloudFront in front of the ALB helps shift the protection layer right to the edge instead of only protecting at the origin server. 

One of the standout features is CloudFront VPC Origin, which allows the ALB to be deployed in a Private VPC but still serve users through CloudFront. This helps reduce the risk of direct access to the backend infrastructure from the Internet.

Additionally, CloudFront can integrate with:
* **AWS Shield Standard:** Protects against network-layer DDoS attacks.
* **AWS WAF:** Filters malicious requests right at the edge, reducing the load on the backend system.
* **AWS Certificate Manager:** Centralized SSL/TLS certificate management.
* **IPv6 and TLS 1.3 support:** Enhances security as well as optimizes connection performance.

By processing traffic right at the edge, many attacks can be prevented before they reach the ALB or application servers.

## 3. Optimizing Operational Costs
![Pricing](../../images/3-BlogsTranslated/cfblog2.png)

Besides improving performance, CloudFront also helps reduce many expenses during system operation.

* **Free Data Transfer Out:** Data Transfer Out (DTO) from AWS Origin to CloudFront is free. Costs primarily arise when CloudFront delivers data to end-users, with pricing being more optimized thanks to tiered pricing models and CloudFront's promotional packages.
* **Automatic data compression:** CloudFront automatically compresses content before sending it to users, helping to reduce the amount of transferred data and save bandwidth costs.
* **Connection reuse:** CloudFront reuses TCP connections to the ALB, reducing the number of new connections that need to be established. This helps reduce the ALB's Load Balancer Capacity Unit (LCU) consumption and contributes to lower operational costs.
* **DNS optimization:** If using Amazon Route 53 with an Alias Record to point a domain name to a CloudFront Distribution, DNS queries for the Alias Record are also not charged.

## 4. Considerations When Transitioning to the CloudFront - ALB Architecture

AWS recommends performing the transition process in phases to mitigate risks. Some best practices include:

* Using Route 53 Weighted Routing to gradually shift traffic from the ALB to CloudFront, instead of moving everything all at once.
* Migrating AWS WAF from the ALB to CloudFront to leverage protection capabilities right at the edge.
* If the ALB uses Host Header Routing, configure CloudFront to forward the Host header so that routing rules still function correctly.
* For an Internet-facing ALB, it is advisable to configure a Custom Header so the ALB only accepts requests coming from CloudFront, avoiding direct access to the origin.
* Adjust Cache policies, Origin Request Policies, and Response Header Policies to suit the application's characteristics to ensure performance and compatibility.

## 5. Other Notable Features

Beyond the main benefits, CloudFront provides many features that support building large-scale systems, such as:
* Support for multi-Region deployment with automatic failover capabilities.
* Processing requests at the edge using CloudFront Functions or Lambda@Edge.
* Support for automatic content compression to reduce bandwidth.
* Integration with CloudWatch to monitor metrics such as Cache Hit Ratio, Origin Latency, and 4xx/5xx error rates, helping to evaluate the system's operational efficiency.

## Conclusion

Combining Amazon CloudFront and an Application Load Balancer helps improve global access performance, enhance security, and optimize operational costs. According to AWS tests, this architecture can significantly improve response times, especially for users far from the deployment region.

Furthermore, features like CloudFront VPC Origin, AWS WAF, AWS Shield, caching mechanisms, data compression, and connection reuse help reduce the load on the backend system while increasing the application's scalability and availability.

For systems serving users globally, deploying CloudFront in front of an ALB is an architecture worth considering to balance performance, security, and costs during operation.

<br>Group Post Link: <https://www.facebook.com/groups/660548818043427/user/100025022862424>

> Reference: [Optimizing application performance: The strategic benefits of combining Amazon CloudFront with Application Load Balancers](https://aws.amazon.com/blogs/networking-and-content-delivery/optimizing-application-performance-the-strategic-benefits-of-combining-amazon-cloudfront-with-application-load-balancers/)