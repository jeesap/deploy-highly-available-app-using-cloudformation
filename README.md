# Deploy a High-Availability Web App using CloudFormation (Infrastructure as Code)

![alt Project Architecture](https://github.com/sergiopichardo/iac-project-2-udacity/resources/iac-project-2-ha-web-app.png)

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