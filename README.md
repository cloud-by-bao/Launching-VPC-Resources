<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**👤 Author:** Bao Luong  
**📧 Email:** baodevops21@gmail.com  
**💼 LinkedIn:** [bluong21](https://www.linkedin.com/in/bluong21/)
---

## Launching VPC Resources

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is AWS's foundational networking service that helps us create our own networks and configure the security/traffic rules and connectivity with internet.

### How I used Amazon VPC in this project

I used Amazon VPC to create my own VPC with different resources/components (e.g. security groups, network ACLs), private resources (e.g. private subnet) and EC2 in both public and private subnets.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the resource map to be interactive and visual which makes it easier to see the entire VPC setup.

### This project took me...

This project took me an hour and half.

---

## Setting Up Direct VM Access

Directly accessing a virtual machine means "logging into" the EC2 instance (instead of just managing a higher level with the AWS Managment Console). This includes operations like installing software and changing my EC2 instance's configurations. 

### SSH is a key method for directly accessing a VM

SSH traffic means Secure Shell, and it is both a protocol and a traffic type. It is the protocol that mathces key pairs and enables direct VM access, and once a connection is set up, it is a traffic type that encrypts communication/date being transferred. 

### To enable direct access, I set up key pairs

Key pairs are tools that help developers/engineers authenticate themselves when trying to get direct access to a virtual machine e.g. an EC2 instance. Key pairs work by having two private key for the VM, and a matching private key for the resource/user.

A private key's file format mean the file that my key is stored in. My private key's file format was .pem, which is a widely accepted file format that most servers will be able to use.

---

## Launching a public server

I had to change my EC2 instance's networking settings by changing the VPC and the subnet of my Ec2 instance was going to be launched in! I updated both to my NextWork VPC and my Public Subnet respectively. I also used my existing Public security group.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because public security group that was created allows in ALL HTTP traffic, which would leave our private server more vulnerable to security attacks/risks. 

My private server's security group's source is my NextWork Public Security Group, which means only SSH traffic coming form resources associated with that goup could be allowed.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I chose VPC and more, which gave me the resource map. 

A VPC resource map is visual diagram that maps out the entire VPC's compenents and the relationships/connections between. 

My new VPC has a CIDR block of 10.0.0.0/16. 

It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPCs are already isolated from each other. Still, this is not best practice if we need VPC peering.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: either none or one in each availability zone for my VPC.

This was because it best practice to improves redundancy and high availbility to have at least one subnet per AZ.

The set up page also offered to create NAT gateways, which are connectors/gateways that will let resources in my private subnet get access to the internet (e.g. for security updates) while still blocking off incoming traffic from the internet.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-networks-ec2_8ee57662)

---

---
