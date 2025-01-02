# Route 53 Private Hosted zone

- This private hosted zone is used to resolve internal conflict, and convert the Private IP addresses of the backend EC2 Instances to domain name. 
- So that the app(Tomcat) server can communicate with backend services using domain name. 
- This is useful, since the private IP address of the instance changes when its terminated and launced again. 
- So, if IP address is mapped with domain name, then the changed private IP address is automatically updated. 
- Which can reduce the interaction with application.properties configuration file.

 ![Private-route](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/Private-route-first.png)

 Select the Region in which your EC2 Instance is launched. In my case, it is Stockholm. Then click on create hosted zone.

 ![Private-route](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/Private-route-second.png)

 Click on your create hosted zone i.e vprofile.in and then click on create record.
 
 Record for MySQL(db01) EC2 Instance

 ![Private-route](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/Private-route-third.png)

  Record for Memcached(mc01) EC2 Instance

 ![Private-route](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/Private-route-fourth.png)

 Record for RabbitMQ(rmq01) EC2 Instance

 ![Private-route](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/Private-route-fifth.png)
