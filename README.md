# AWS Task-3 – S3, EC2 & Application Load Balancer

## 📌 Task Overview
This project demonstrates the implementation of core AWS services by creating a secure S3 bucket, capturing logs using CloudWatch, and deploying two EC2 instances behind an Application Load Balancer to distribute incoming traffic.

---

## 🛠️ Services Used
- AWS S3  
- AWS EC2  
- AWS Application Load Balancer (ALB)  
- AWS CloudTrail  
- AWS CloudWatch  

---

## 🔐 Part 1: Amazon S3 (Private Bucket & Logging)

### ✔️ S3 Bucket Configuration
- Created an S3 bucket with **all public access blocked**
- Uploaded sample files to the bucket
- Ensured the bucket is private and secure

### ✔️ Logging with CloudWatch
- Enabled **AWS CloudTrail** to capture S3 management events
- Configured CloudTrail to send logs to **Amazon CloudWatch Logs**
- Verified S3 actions such as `PutObject` and `GetObject` in CloudWatch

📸 Screenshots included in the `screenshots/` folder.

---

## 🖥️ Part 2: EC2 Instances & Application Load Balancer

### ✔️ EC2 Setup
- Launched **two Amazon Linux EC2 instances**
- Installed and configured Apache (`httpd`) web server
- Each instance serves a simple HTML response to identify it uniquely

### ✔️ Application Load Balancer
- Created an **Internet-facing Application Load Balancer**
- Configured an HTTP listener on **port 80**
- Created a target group and registered both EC2 instances
- Verified that both targets are **healthy**

### ✔️ Traffic Distribution
- Incoming HTTP traffic is routed through the ALB DNS endpoint
- Requests are distributed across both EC2 instances

📸 Screenshots included to show:
- ALB status (Active)
- Listener and target group configuration
- Healthy targets
- Browser / curl output

---

## 🌐 Notes on Network Access
In some environments, outbound HTTP traffic may be restricted by local network or ISP policies.  
The Application Load Balancer and target group were verified healthy, and DNS resolution was confirmed using public DNS servers.

---
