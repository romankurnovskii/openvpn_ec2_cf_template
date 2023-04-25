# OpenVPN on AWS EC2 with CloudFormation

A quick and easy way to set up and maintain your own VPN using the open-source version of OpenVPN on an Amazon Web Services (AWS) EC2 instance.

## Features

- Simple setup using AWS CloudFormation
- OpenVPN server on an AWS EC2 instance
- Configurable instance type and region
- Automatic client configuration generation
- Secure key storage in an S3 bucket
- Automated server updates and maintenance

## Quick Start

- Sign in to your [AWS Management Console](https://console.aws.amazon.com/)
- Click on the "Create Stack" button in the [CloudFormation Console](https://console.aws.amazon.com/cloudformation/home)
- Upload the provided CloudFormation template and follow the prompts
- Once the stack creation is complete, go to the **Outputs** tab in CloudFormation to find the S3 URL for your client configuration
- Download the client configuration file (`client.ovpn`) and use it with your OpenVPN client software

## Details

### Cost

The cost of running this VPN solution mainly depends on the selected EC2 instance type and the data transfer. The default instance type is **t3a.nano**, which should be sufficient for most personal VPN use cases. 

The cost for this instance type is approximately **$3-4/month**, depending on the region for instance **ondemand**. Current setup is for spot, so it can be **~$1-2/month**.


### Technical Details

This project uses AWS CloudFormation to create and manage the following resources:

- EC2 instance (Ubuntu) with OpenVPN server 
- EC2 security group for allowing VPN and SSH access
- Elastic IP address associated with the EC2 instance
- S3 bucket for securely storing client configurations
- IAM role and policies for granting necessary permissions
- The provided Bash scripts automate the installation and configuration of OpenVPN, as well as generating client configuration files.
