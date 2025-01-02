# Output Validation for the Project.
1. http connection
2. https connection

- For http connection copy and paste the LoadBalancer DNS Name in Browser.
![http-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-first.png)
![http-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-second.png)

- For https secure connection copy and paste the Record Name from Public Hosted zone of Route 53.
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-third.png)

Enter the following URL in the browser: 
> https://vprofileapp.southlake.xyz

![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-fourth.png)

This shows that the website is deployed by a valid https certificate holder. Which gives the user a sense of security while accessing the webpage. Since the data is passed through the browser in an encrypted way, to prevent any data breaches.

![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-fifth.png)

Username and password to login :
> admin_vp

If you logged in successfully, then it means the MySQL connection is working properly.
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-sixth.png)

Then click on All Users button
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-seventh.png)

Click on User Id 4 for testing
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-eighth.png)

Data of User Id 4 is retrieved from Database
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-nineth.png)

Now again click on the same User Id for testing Memcached service
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-tenth.png)

Now it can be seen that the data is been retrieved from cache Memory, instead of database, this helps to reduce the load of database by storing already accessed data to Cache Memory.

![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-eleventh.png)

For verifying RabbitMQ service 
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-twelfth.png)

It can be seen that the queue is generated successfully
![https-validation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/validation-thirteenth.png)
---
Following is the reference for [CloudStack-VProfile](https://github.com/Kizhakkekkara-Vishnu-Vijayan/CloudStack-VProfile.git "Github Link") project were the same deployment is done in local machine using virtual machines, and automating the virtual machine creation using Vagrant.
This can act as a good foundation for learning deployment in AWS cloud. 