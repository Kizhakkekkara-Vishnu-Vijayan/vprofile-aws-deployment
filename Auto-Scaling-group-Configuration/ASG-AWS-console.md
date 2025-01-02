# Auto Scalling Group configuration

For creating ASG we need to create the following 
1. AMI 
2. Launch Template 
3. Auto Scaling Groups

## AMI creation steps :
![AMI creation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-first.png)
![AMI creation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-second.png)
![AMI creation](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-third.png)

## Launch Template creation steps :
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-fourth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-fifth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-sixth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-seventh.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-eighth.png)

## ASG creation steps :
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-nineth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-tenth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-eleventh.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-twelfth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-thirteenth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-fourteenth.png)
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-fifteenth.png)

- Enable stickiness in Target group so that the LoadBalancer's cookie is used whenever the user is loggin in.
- This is specific to vprofile project since only the app01 is configured to authenticate the user.
- So when enabled stickiness the ELB will forward the traffic to app01 instance only.

![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-sixteenth.png)

Health check status for EC2 instance created by Target Group i.e vprofile-app. 
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-seventeenth.png)

You can see that the vprofile-app EC2 Instance is created automatically with the help of ELB.
![Launch Template](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/asg-eighteenth.png)