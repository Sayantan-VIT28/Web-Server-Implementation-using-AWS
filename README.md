# 🔐 Secured Web Server Implementation

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazon-aws)
![EC2](https://img.shields.io/badge/Amazon-EC2-blue?style=for-the-badge&logo=amazon-ec2)
![VPC](https://img.shields.io/badge/Amazon-VPC-purple?style=for-the-badge)
![ALB](https://img.shields.io/badge/Application-Load%20Balancer-green?style=for-the-badge)

## 📌 Project Overview

This project demonstrates the implementation of a **Secured Web Server** using **Amazon Web Services (AWS)**.

The architecture is created using AWS resources including a custom **VPC, public and private subnets, Internet Gateway, Route Tables, EC2 instances, Security Groups, Target Group, and Application Load Balancer**.

The main objective is to deploy web servers on different EC2 instances and use an **Application Load Balancer** to access and distribute requests between the servers.

---

## 🎯 Objectives

- Create a custom AWS VPC.
- Create public and private subnets.
- Configure an Internet Gateway.
- Configure public and private route tables.
- Associate subnets with their respective route tables.
- Launch EC2 instances in different subnets.
- Configure security groups.
- Install and configure web servers.
- Create a Target Group.
- Configure an Application Load Balancer.
- Access the web servers using the ALB DNS name.
- Demonstrate successful communication between the servers and load balancer.

---

## 🏗️ AWS Architecture

```text
                         🌐 Internet
                              |
                              v
                  +------------------------+
                  | Application Load       |
                  |      Balancer          |
                  +-----------+------------+
                              |
                       +------+------+
                       | Target Group|
                       |  my-group   |
                       +------+------+
                              |
                    +---------+---------+
                    |                   |
                    v                   v
              +-----------+       +-----------+
              |   EC2-1   |       |   EC2-2   |
              | Web Server|       | Web Server|
              |  Public   |       |  Private  |
              +-----------+       +-----------+
                    |                   |
                    +---------+---------+
                              |
                         +----v----+
                         |  VPC    |
                         | my_vpc  |
                         +----+----+
                              |
                    +---------v---------+
                    | Internet Gateway  |
                    |   my_internet     |
                    +-------------------+
