# Artifact Build using maven

- Before running the maven build command. First you need to edit the application.properties file and include the correct hostname which the Private Route 53 has assigned. i.e db01.vprofile.in, mc01.vprofile.in, rmq01.vprofile.in 
- It is done before maven build because, after running the command it will create a folder named target, in which there will be application.properties file, which will be used for backend communication.

Now clone the git repository using :-

> git clone https://github.com/hkhcoder/vprofile-project.git

After cloning the repo edit the application.properties file, with proper hostname as mentioned in the private route 53 records section.

Open git bash in vscode and run the following command and check for the maven and java version for compatibility.

```
Vishnu@DESKTOP-NMCOA6P MINGW64 /e/hkhcoder-sample/vprofile-project (main)
$ mvn -version
Apache Maven 3.9.9 (8e8579a9e76f7d015ee5ec7bfcdc97d260186937)
Maven home: C:\ProgramData\chocolatey\lib\maven\apache-maven-3.9.9
Java version: 17.0.12, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-17
Default locale: en_US, platform encoding: Cp1252
OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
```
Run the following command to check whether the AWSCLI is installed:

```
Vishnu@DESKTOP-NMCOA6P MINGW64 /e/hkhcoder-sample/vprofile-project (main)
$ aws

usage: aws [options] <command> <subcommand> [<subcommand> ...] [parameters]
To see help text, you can run:

  aws help
  aws <command> help
  aws <command> <subcommand> help

aws: error: the following arguments are required: command
```
If every thing is fine then you are good to go.

Run the maven build command :
> mvn install 

   ![maven build](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/maven-first.png)

After that run following commmand :
> aws configure

It will ask for AWS Access Key ID and AWS Secret Access Key. This ID and Access Key were provided when we create the IAM user. Enter the correct credentials to get access.

After that run the following command to copy the vprofile-v2.war from local machine to aws s3 bucket :

> aws s3 cp target/vprofile-v2.war s3://vprofile-las-artifact-1405/

Then Run the command to verify that the Artifact is present inside the S3 Bucket :

```
Vishnu@DESKTOP-NMCOA6P MINGW64 /d/hkhcoder/vprofile-project (awsliftandshift)
$ aws s3 ls s3://vprofile-las-artifact-1405/
2024-12-30 23:27:03   83278614 vprofile-v2.war
```
- After you have pushed the Artifact into S3, now its time to copy the artifact from S3 to app01 EC2 Instance.
- Get the public IP Address of the app01 EC2 Instance.
- Now to loggin into Instance write the below command in the directory where the keypair of AWS exists.
- ssh -i <keypair_name.pem> ubuntu@\<Public-IP>

After logging into app01 Instance you need to download AWS-cli so that you can copy the content of S3 Bucket using the AWS-cli.

Command to Install AWS-cli :
> snap install aws-cli --classic

Command to copy S3 bucket content into app01 EC2 Instance :

```
aws s3 cp s3://vprofile-las-artifacts-1405/vprofile-v2.war /tmp/
systemctl stop tomcat10
systemctl daemon-reload
rm -rf /var/lib/tomcat10/webapps/ROOT
cp /tmp/profile-v2.war /var/lib/tomcat10/webapps/ROOT.war
systemctl start tomcat10
ls /var/lib/tomcat10/webapps/
```
![Tomcat-deploy](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/maven-second.png)

Remove the default tomcat website using :
> rm -rf /var/lib/tomcat10/webapps/ROOT

Command to copy the Artifact into the tomcat's default deployment directory
> cp /tmp/profile-v2.war /var/lib/tomcat10/webapps/ROOT.war

To launch the website, start the tomcat service using :
> systemctl start tomcat10

Check whether the ROOT.war file is extracted automatically by tomcat server using :
> ls /var/lib/tomcat10/webapps/

![Tomcat-deploy](https://github.com/Kizhakkekkara-Vishnu-Vijayan/vprofile-aws-deployment/blob/master/AWS-Console-SS-All/maven-third.png)