# Load Balancer Configuration

For Load Balancer we have to first create a Target group, in our case app01, so that the traffic is distributed into multiple availability zone for the selected target.

## Steps for creating Target Group

![Target-group-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-first.png)
![Target-group-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-second.png)
![Target-group-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-third.png)
![Target-group-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-fourth.png)
![Target-group-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-fifth.png)

## Steps for creating Load Balancer

![Load-Balancer-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-sixth.png)
![Load-Balancer-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-seventh.png)
![Load-Balancer-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-eighth.png)
![Load-Balancer-console](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/elb-nineth.png)

Now add Load Balancer DNS name in Route53 public hosted zone records.

Add Record Name :
> vprofileapp.southlake.xyz

Add Record type :
> CNAME 

Add value :
> vprofile-las-elb-419405719.eu-north-1.elb.amazonaws.com

![public-route-cosole](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/public-route-fifth.png)

So whenever the domain name is entered it is resolved to its DNS name and the traffic is routed to the LoadBalancer.