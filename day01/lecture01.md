#  Cloud Essentials 1.0 [ July 2019]

This guide provides simple practical steps to understanding AWS Cloud

---

##

You will be put in a real life scenario (as a DevOps specialist) to use cloud technology provide practical soultions.

---

## Intended Audience

Users who undertand basic concept of the computer system.

---

## Requirements

Ensure you have gone through requirements documentation


**DO NOT PROCEED UNTIL THIS IS SORTED**

---

## Getting started

- Make sure you have created an account in AWS and your login works

---

###  Task 1 [EC2 ] : Virtual Machine Provisioning, (Understanding AMI/Instancr types): Your boss has asked you to "quickly" provision a box in Amazon cloud, with the following requirements:
'Windows Server 2019'. Instance should be a free tier, with 1 GB M/M and CPU. It

- Should be Windows Server 2019
- Instance should be a free tier, with 1GB memory about CPU
- Should be accessible over the Internet
- Login to the instance and confirm everything works.

#### Task 2 [IAM] : Create a super account policy that give power users "Root" permission. This will be assigned to the DevOps team. Call it 'DevOps-Access'

 ```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}

```
#### Task 3 [IAM]:  Create two user accounts; developer01 and devops01. Assign 'AWSCodeBuildDeveloperAccess' policy to 'developer01' and 'Devops-Access' to 'devops01'


#### Task 4 [AWS CLI]: Install AWS CLI on your local machine. Use the link provided in Dropbox to install
- After installing, go on the command line, type 'aws', to confirm it's been successfully installed
- Configure profile accounts for developer01 and devops01 users

    aws configure --profile developer01
    aws configure --profile devops01
    aws configure list

#### Task 5 [ Using AWS CLI ]: Use the cli to query for running AWS instance and provide instanceID and IP adddress

- get a feel of how to use the cli: aws [command] help is a good starting point. eg aws ec2 help
- [aws ec2 describe-instances]. This will return a json output. Install [jq] command utility to help tame the json output
- Open a new commmand line as Administrator, then run ```chocolatey install jq```
- aws ec2 describe-instances | jq -r ".Reservations[] | .Instances[] | .InstanceId"
- aws ec2 describe-instances | jq -r ".Reservations[] | .Instances[] | .PublicIpAddress"
- aws ec2 describe-instances | jq -r ".Reservations[] | .Instances[] | .InstanceId, .PublicIpAddress"

#### Task 6. Use the CLI to create a name tag for the running instance. Call it 'TestInstance'
- aws ec2 create-tags --resources xxxxxxxxxx --tags Key=Name,Value=TestInstance


#### Task 7. Use the CLI to create 2 new Windows VM  instances similar to one priviously provisioned. Tag them as InstanceA and InstanceB
- aws ec2 run-instances --image-id ami-03855eb1640d145f6 --count 2 --instance-type t1-micro --profile devops01
- aws ec2 create-tags --resources xxxxxxxxxx --tags Key=Name,Value=InstanceA
- aws ec2 create-tags --resources xxxxxxxxxx --tags Key=Name,Value=InstanceB

#### Task 8: Terminate the instances
- aws ec2 Terminate-instances --instance-ids xxxxxxxxxxxxxx xxxxxxxxxxxxxxx


#### Task 9: Install Apache Web Server on the first node created.Use the node to host this static page: http://www.2createawebsite.com/templates2/Technology.zip
- http://archive.apache.org/dist/httpd/binaries/win32/apache_2.2.13-win32-x86-no_ssl.msi


#### Task 10: Create  Amazon Linux VM instance and log to it


