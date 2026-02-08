<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** MD. Fahim Parvez  
**Email:** parvez22205341185@diu.edu.bd

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a logically isolated virtual network in AWS where you can launch and manage cloud resources such as EC2 instances, databases, and load balancers.

It is useful because it allows you to control IP addressing, subnets, routing, and security, giving you a secure and customizable environment for both public and private resources.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a secure network environment where I could launch public and private subnets, configure route tables, attach an Internet Gateway, set up security groups and network ACLs, and deploy EC2 instances, ensuring proper traffic flow, access control, and connectivity testing.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the level of detail and coordination required to configure a working VPC with proper connectivity and security.

### This project took me...

This project took me about two hours in total.

---

## Connecting to an EC2 Instance

Connectivity means the ability of systems or resources to communicate with each other over a network, sending and receiving data successfully without being blocked by routing or security rules.

My first connectivity test was whether I could connect to my public server or EC2 instance

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is an AWS-managed service that allows secure SSH access to EC2 instances directly from the AWS Management Console, without needing to download or manage a private key file locally.

My first attempt at getting direct access to my public server resulted in an error, because the required security group rules and connectivity settings (such as allowing SSH traffic on port 22 and ensuring the instance had a public IP and a route to the Internet Gateway) were not fully configured at that time.

I fixed this error by updating my security group to allow inbound SSH traffic on port 22 from the correct source and confirming that my EC2 instance had a public IP address and a route to the Internet Gateway.

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a network diagnostic tool that uses ICMP (Internet Control Message Protocol) to check whether one system can reach another over a network.

I used ping to test the connectivity between my public EC2 instance and my private EC2 instance, confirming that they could communicate within the VPC.

The ping command I ran was
ping 10.0.1.153
This allowed me to send ICMP requests from my public EC2 instance to my private EC2 instance to verify internal connectivity within the VPC.

The first ping returned a timeout or no response. This meant that ICMP traffic was being blocked by the security group or network ACL, or that the necessary rules allowing ping traffic had not yet been configured.

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by checking and updating the security group and network ACL rules to allow ICMP traffic, verifying that the private EC2 instance’s security group permitted inbound traffic from the public EC2 instance, and confirming that both instances were in the same VPC with correct routing.

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a command-line tool used to transfer data to or from a server over a network, commonly via protocols like HTTP, HTTPS, FTP, or others. It’s often used to test connectivity to web servers or APIs.

I used curl to test the connectivity between my public EC2 instance and an external website or server on the internet (for example, https://www.google.com) to confirm that the instance had proper internet access.

### Ping vs Curl

Ping and curl are different because ping uses ICMP to simply check whether a host is reachable and measures response time, while curl uses application-layer protocols like HTTP/HTTPS to actually send and receive data from a server, allowing you to test real service connectivity, not just network reachability.

---

## Connectivity to the Internet

I ran the curl command (curl https://learn.nextwork.org/projects/aws-host-a-website-on-s3), which returned that curl has fetched the complete HTML content of NextWork's web app

![Image](http://learn.nextwork.org/relieved_purple_wise_freshwater_mussel/uploads/aws-networks-connectivity_8ee57662)

---

---
