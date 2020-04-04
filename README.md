# Deploy a High-Availability Web App using CloudFormation (Infrastructure as Code)

## Overview 
First use *network.yml* and *network.json* files to create the networking infrastructure for udagram including VPC, Subnets, Internet Gateway, Route Tables, and Routes. Then, use *servers.yml* and *servers.json* to launch the server resources and the create IAM role, policy and profile needed to access resources (udacity.zip) stored in S3 bucket. 

## The following files/directories are included: 
- **network.yml**: Cloudformation template for networking infrastructure 
- **network.json**: Cloudformation parameters for network.yml 
- **servers.yml**: Cloudformation template for server resources 
- **/resources**: Lucid Charts Architecture Image and udacity.zip 
- **create.sh**: Shell script to launch and create aws cloud resources 
- **update.sh**: Shelll script to update cloud resources
- **delete.sh**: Shell script to delete CloudFormation stack by name. 

## Note: Change permissions to be able to execute files 
```sh
$ sudo chmod 755 network.yml servers.yml
```

## Example 1: Creating a CloudFormation Network stack  
```sh
$ ./create.sh UdagramNetwork network.yml network.json 
```

## Example 2: Update a CloudFormation Network stack  
```sh
$ ./update.sh UdagramNetwork network.yml network.json 
```

## Example 3: Delete Cloudformation stack by name
```sh
$ ./delete.sh UdagramNetwork 
```

![alt Project Architecture](https://github.com/sergiopichardo/deploy-highly-available-app-using-cloudformation/blob/master/resources/iac-project-2-ha-web-app.png)

## Specifications 
### The Basics 
- [x] Parameters 
    - [x] Contains a moderate amount of parameters 
- [x] Resources 
    - [x] Load Balancer 
    - [x] Launch Configuration 
    - [x] Autoscaling Group 
    - [x] Target Group 
    - [x] Load Balancer Security Group 
    - [x] Load Balancer 
    - [x] Load Balancer Listener 
- [x] Outputs 
    - [x] URL here with the Load Balancer DNS and "http" in front of it. 
- [x] Working Test 
    - [x] Web page say "it works! Udagram, Udacity"

### Load Balancer 
- [x] Target Group
    - [x] Target group has property that associates Auto Scaling Group with Target Group
    - [x] Load Balancer has Listener Rule associated with the same target group 
- [x] Health Check and Listener 
    - [x] Port 80 is used in Security Groups, Health Checks, and Listeners associated with the Load Balancer. 

### Auto-Scaling 
- [x] Subnets 
    - [x] Auto Scaling Instances using PRIV-NET (private subnets) for auto-scaling instances 
- [x] Machine Specs 
    - [ ] The machine should have 10 GB or more of disk and should be a t3.small 
- [x] No SSH Key 
    - [x] Launch configuration does not have 'keyName' property