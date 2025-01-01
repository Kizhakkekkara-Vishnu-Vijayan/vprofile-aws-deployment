## vprofile Backend (MySQL, Memcached, RabbitMQ) security group

Create Security group named vprofile-backend-sg

 ![Backend Security group](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/vprofile-backend-sg-first.png)

Allows traffic from app(Tomcat) Instance to MySQL(3306), Memcached(11211), RabbitMQ(5672) Instances, and allows SSH(22) using local system IP.

And allow all backend instances to communicate with each other, by providing own security group to itself.

 ![Backend Security group](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/vprofile-backend-sg-second.png)