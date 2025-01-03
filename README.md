# VPROFILE AWS Deployment Project

## Overview
This project demonstrates the deployment of a multi-tier web application (VPROFILE) on AWS using services like EC2, S3, Route 53, ELB, and Auto Scaling. The application backend is built with technologies like Tomcat, MySQL, RabbitMQ, and Memcached.

## Project Description
VPROFILE Deployment on AWS is a project that showcases the deployment of a scalable, secure, and multi-tier web application leveraging AWS cloud services. This application demonstrates how modern cloud infrastructure can be used to achieve reliability, scalability, and cost-effectiveness for enterprise applications.

The application is built on a multi-tier architecture with components deployed across several AWS services:
1. **Application Layer:** Hosted on Amazon EC2 instances running Tomcat for serving dynamic content.
2. **Database Layer:** Utilizes MySQL deployed on a dedicated EC2 instance for persistent storage.
3. **Message Broker Layer:** Configured RabbitMQ for asynchronous communication between application components.
4. **Caching Layer:** Includes Memcached to optimize application performance.

### Key Features of the project include:
---
- **Load Balancing:** AWS Elastic Load Balancer (ELB) replaces NGINX to distribute incoming traffic across instances, ensuring high availability.
- **Auto Scaling:** Auto Scaling Groups (ASG) dynamically manage the number of instances to handle varying traffic loads.
- **Artifact Management:** The application build artifact is stored in Amazon S3 and deployed to Tomcat instances using Maven.
- **Domain Management:** Route 53 provides hostname resolution for internal communication and integrates with a custom domain purchased on GoDaddy.
- **Security:** HTTPS is enforced using an SSL certificate issued by AWS Certificate Manager (ACM).

## Getting Started
To get started with VPROFILE AWS Deployment Project you need to have basic familiarity with AWS services like EC2, S3, Elastic Load Balancer, Auto Scaling Groups, Target Groups, Launch Templates, and Route 53. 

### Prerequisites
1. An active AWS account.
2. A purchased domain name (e.g., from GoDaddy).
3. Installed the following tools on your local system:
   - AWS CLI
   - Maven and JDK
   - Git
4. A suitable code editor (eg. VScode)

## Setup Overview
1. **Cloning Repository:** Clone the Repository: Start by cloning the project repository to your local machine.
2. **Infrastructure Provisioning:** Use AWS console to create and configure AWS resources, including EC2 instances for application components (Tomcat, MySQL, RabbitMQ, Memcached), Auto Scaling Groups (ASG) for scalability, and an S3 bucket for artifact storage.
3. **Service Configuration:** Automate the setup of services on EC2 instances using user data scripts written in Bash. These scripts install dependencies and configure Tomcat, RabbitMQ, MySQL, and Memcached.
4. **Domain and Routing:** Use Route 53 to map private IPs to hostnames for internal communication and link the application to a custom domain purchased on GoDaddy.
5. **Security and Load Balancing:** Configure an AWS Elastic Load Balancer (ELB) with an SSL certificate from AWS Certificate Manager (ACM) to enable HTTPS traffic and evenly distribute incoming requests, by editing the inbound rules of security groups.
6. **Final Verification:** Verify the deployment by accessing the application via the custom domain and ensuring all components work seamlessly.

 This structured approach combines automation, scalability, and security to deploy the application effectively.

 ## Project flow diagram
 ![Project flow diagram](https://github.com/Kizhakkekkara-Vishnu-Vijayan/Sample/blob/master/AWS-images/Flow-diagram.png)

## Project Flow execution steps :
1. Login to AWS Account
2. Create Key Pairs
3. Create Security Groups

[AWS-Security-groups](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/AWS-Security-groups)
```
├───AWS-Security-groups
│   ├───vprofile-app
│   │   └───vprofile-app-sg.md
│   ├───vprofile-backend
│   │   └───vprofile-backend-sg.md
│   └───vprofile-ELB
│       └───vprofile-ELB-sg.md
```
 4. Launch Instances with user data [BASH SCRIPTS]

[Deployment-Scripts](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Deployment-Scripts)

```
├───Deployment-Scripts
│   ├───memcache.sh
│   ├───mysql.sh
│   ├───rabbitmq.sh
│   └───tomcat_ubuntu.sh
```
 5. Update IP to name mapping in route 53

[Route-53-setup](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Route-53-setup)

```
├───Route-53-setup
│   ├───Private-Route
│   │   └───Private-Route-config.md
```
 6. Build Application from source code
 7. Upload to S3 bucket
 8. Download Artifact to Tomcat EC2 Instance

 [Build-Deploy-Artifacts](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Build-Deploy-Artifacts)

 ```
 ├───Build-Deploy-Artifacts
│   ├───AWS-IAM-console.md
│   ├───AWS-S3-console.md
│   ├───Maven-Build.md
│   └───README.md
```
9. Setup ELB and HTTPS [Certificate from ACM]

[Load-Balancer](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Load-Balancer-Configuration)
[Route-53-setup](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Route-53-setup)

```
├───Load-Balancer-Configuration
│   ├───ELB-console.md
├───Route-53-setup
│   ├───Public-Route
│   │   └───ACM-console.md
```
10. Map ELB Endpoint to website name in Godaddy-DNS/Route53

[Route-53-setup](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Route-53-setup)

```
├───Route-53-setup
│   ├───Public-Route
│   │   └───Public-Route-config.md
```
11. Build Autoscaling Group for Tomcat Instances

[Auto-Scaling-group-Configuration](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Auto-Scaling-group-Configuration)

```
├───Auto-Scaling-group-Configuration
│   ├───ASG-AWS-console.md
```

12. Verify

[Output-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/Output-validation.md)

```
├───Output-validation.md
```
13. AWS Cost Incured during project implementation

[AWS-Billing](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/tree/master/AWS-Billing.md)

```
├───AWS-Billing.md
```

