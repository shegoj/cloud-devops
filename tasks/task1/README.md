# Network Stack on AWS ablnd RDS

## Goal

Learn how to manage Network Stack on AWS which consists of VPC resources and put infrastucture on it


You have been given 10.0.0.0/24 network to use to create  2 EC2 nodes, and a RDS DB (postgres "9.6.8").
Set the 2 EC2 nodes on a public subnet each  and the DB on a private subnet


## resources

1. Explore Terraform Registry - [https://registry.terraform.io](https://registry.terraform.io).
1. Explore examples of using [terraform-aws-vpc module](https://github.com/terraform-aws-modules/terraform-aws-vpc/tree/master/examples).
1. Using [terraform-aws-vpc module](https://github.com/terraform-aws-modules/terraform-aws-vpc/)



## tasks

1. Verify that EC2 instances have been launched

1. Connect to EC2 instance by SSH (eg, using EC2 keypair)

1. Ensure you are able to connect to the database from each of the 2 nodes

