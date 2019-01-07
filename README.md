# aws-2-zone-vpc-cf-template

## Description:

This solution creates an [AWS VPC](https://aws.amazon.com/vpc/) environment that has 2 public zones and 2 private zones.

The AWS CloudFormation template creates a AWS VPC with 2 public subnets and 2 private subnets along with appropriate outbound routing for public subnets to use an AWS Internet Gateway and private subnets to use a AWS NAT Gateway.

Amazon Virtual Private Cloud (Amazon VPC) lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.

_***note AWS NAT Gateway and Elastic IP will incur costs**_

* [NAT Gateway pricing](https://aws.amazon.com/vpc/pricing/) resource used in example: 2 Nat Gateway's
* [Elastic IP pricing](https://aws.amazon.com/ec2/pricing/on-demand/) resource used in example: 2 Elastic IP's

## Prerequisites:

* AWS account and environment configured with AWS Credentials
* IAM user with AWSCloudFormationReadOnlyAccess, AmazonVPCFullAccess, AmazonEC2FullAccess

## See how it works:

AWS Management Console

* Login to AWS Management Console
* Launch in CloudFormation 2-zone-vpc-cf-template.yml (from the repo you cloned)

CloudFormation Fields

* Stack name (Enter a name to associate to your AWS VPC deployment)
* Environment Name (Name to describe the VPC environment)**Next**
* Continue choosing **Next**
* Click **Create**

## Test:

In the AWS Management Console you should be able to verify the following have been created:

* 1 Public Subnet 10.0.10.0/24 (Zone A)
* 1 Private Subnet 10.0.20.0/24 (Zone A)
* 1 Public Subnet 10.0.30.0/24 (Zone B)
* 1 Private Subnet 10.0.40.0/24 (Zone B)
* 5 Route table entries to route either within 10.0.0.0/16 or to the either the Internet Gateway or NAT Gateway for outbound
* 1 Internet Gateway
* 2 NAT Gateways for outbound traffic of private zone a and b
* 2 Elastic IP addresses associated to respective NAT Gateway's
