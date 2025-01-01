# Build and Deploy

In this section the artifact containing the application will be build using maven.Then it will be pushed into an S3 bucket. Then form S3 bucket the Artifact will be copied to app01(Tomcat) EC2 instance.

Following are the requirements for this section :-
1. An AWSCLI for pushing Artifact into S3 bucket
2. An IAM user(vprofile-s3-admin) with S3FullAccess permission. So, that we can configure the IAM user using AWSCLI and push the Artifact into S3.
3. An IAM Role(S3-admin) for EC2 instance with S3FullAccess, so that the Artifact of S3 can be copied to EC2 Instance.
4. Modifying the IAM role for tomcat(app01) EC2 Instance, with the IAM Role(S3-admin) which we created having S3FullAccess permission.

 ![Architectural Diagram](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/build-deploy-diagram.png)