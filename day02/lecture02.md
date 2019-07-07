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

###  Task 11 [EC2 ] : Ensure the static web page running on Apache Windows Server is publicly accessible

- Update EC Instance Security group to allow inbound http traffic for all Users
- Connect to the Windows node and Update Firewall settings to all Apache traffic
- Test that the link is publicly accessible
- Share your link with others and make sure they are able to acces

###  Task 12 [EC2 ] : Lock down access to the website so that only you can access it remotely

- Update EC Instance Security group to allow inbound http traffic only for "custom source". You should now stop using default Security Policies


###  Task 13 [ELB ] : Add a load balancer in front of the EC2  so that HTTP traffic is sent from the LB to Apache on the EC2 node

- Configure the load balancer accordingly


###  Task 14 [EBS ] : Due to high traffic envisaged, configure Apache to log error informtion to a new mount/drive. Call this new drive d:\, create a log directory ( logs), then point Apache to use it

- Here discuss how this is configured and possible use cases.

###  Task 15 [EC2-Linux ] : Install Apache Web Server on the Linux node. Check that is it remotely accessible

- Connect to the node via Putty
- run ``` sudo yum install httpd -y``` to install Apache web Server
- run ``` sudo service start httpd``` to start Apache web Server


###  Task 16 [EC2-Linux ] : Update Apache on Linux home page display "Hello Linux 1"


###  Task 17 [EC2-Snapshot ] : Create 2 new Apache Linux node, just as the previous one. You will end up with 3 Linux nodes

###  Task 18 [EC2-Linux ] : Update Apache on  the new Linux nodes  home page display to "Hello Linux 2" and "Hello Linux 3" respectively


###  Task 19 [EC2-Linux ] :Update the all the 3 Linux nodes so that Apache is publicly acccessible


###  Task 20 [EC2-Linux ] :Now add the 3 nodes to the elastic load balancer. The load balancer should now distribute traffic accros the 4 nodes


#### Task 21 [S3] : You boss has reasoned that it may be cheaper to host the website on a Simple Storage Service (S3). He has asked you to test and migrate to S3 bucket
#### Todo :  Install S3 command line tool to help facilitate upload of artefact to the S3 bucket


