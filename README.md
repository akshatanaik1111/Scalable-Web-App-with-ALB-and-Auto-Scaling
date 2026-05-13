# Scalable-Web-App-with-ALB-and-Auto-Scaling
AWS project demonstrating scalable web application deployment using Application Load Balancer (ALB) and Auto Scaling Group for high availability and traffic management.

# Scalable Web App with ALB and Auto Scaling

## 📌 Project Overview

This project demonstrates how to deploy a scalable and highly available web application on AWS using Application Load Balancer (ALB) and Auto Scaling Group.

The main purpose of this project is to automatically manage increasing traffic loads without crashing the application. The infrastructure automatically distributes traffic across multiple EC2 instances and launches additional instances whenever traffic increases.

This project helps in understanding real-world cloud infrastructure and scalable deployment architecture used in modern applications.

---

# 🎯 Objective

- Handle high traffic efficiently
- Improve application availability
- Automatically scale EC2 instances
- Distribute traffic using Load Balancer
- Build fault-tolerant AWS infrastructure

---

# 🧰 AWS Services Used

## 1. Amazon EC2
Used to launch virtual servers for hosting the web application.

## 2. Application Load Balancer (ALB)
Used to distribute incoming traffic across multiple EC2 instances.

## 3. Auto Scaling Group
Automatically launches or terminates EC2 instances based on traffic conditions.

## 4. Target Group
Connects EC2 instances with the Load Balancer.

## 5. Security Groups
Controls inbound and outbound traffic for secure communication.

## 6. AWS VPC
Provides isolated networking environment for the infrastructure.

---

# 🏗️ Project Architecture

The architecture of this project includes:

1. Creating EC2 instances for hosting the application.
2. Configuring Security Groups for secure access.
3. Creating a Target Group.
4. Creating an Application Load Balancer.
5. Connecting ALB with Target Group.
6. Creating Launch Template for EC2 configuration.
7. Creating Auto Scaling Group.
8. Testing scalability and load balancing.

---

# ⚙️ Step-by-Step Implementation

## Step 1: Launch EC2 Instance

- Open AWS Console
- Go to EC2 Dashboard
- Click Launch Instance
- Select Amazon Linux AMI
- Choose instance type
- Configure Security Group
- Allow:
  - HTTP (Port 80)
  - SSH (Port 22)

---

## Step 2: Install Web Server

Connect EC2 instance using SSH and run:

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

Create sample webpage:

```bash
echo "Welcome to Scalable Web App" | sudo tee /var/www/html/index.html
```

---

## Step 3: Create Target Group

- Go to EC2 Dashboard
- Select Target Groups
- Create Target Group
- Choose:
  - Target type: Instances
  - Protocol: HTTP
  - Port: 80
- Register EC2 instances

---

## Step 4: Create Application Load Balancer

- Go to Load Balancers
- Create Application Load Balancer
- Choose Internet-facing
- Add Listener:
  - HTTP : 80
- Select Security Group
- Attach Target Group

---

## Step 5: Create Launch Template

- Go to Launch Templates
- Create Launch Template
- Configure:
  - AMI
  - Instance Type
  - Security Group
  - User Data Script

User Data Script:

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
echo "Scalable Web App Running" > /var/www/html/index.html
```

---

## Step 6: Create Auto Scaling Group

- Go to Auto Scaling Groups
- Create Auto Scaling Group
- Select Launch Template
- Configure:
  - Minimum instances
  - Maximum instances
  - Desired capacity
- Attach Load Balancer
- Enable scaling policies

---

## Step 7: Test Application

- Copy ALB DNS URL
- Open in browser
- Verify webpage loads successfully
- Test scaling by increasing traffic

---

# 📸 Project Screenshots

## 🔹 Load Balancer



![Load Balancer](Load%20Balancers.png)

---

## 🔹 Auto Scaling Group

![Auto Scaling](Auto%20Scaling.png)

---

## 🔹 EC2 Instances

![EC2 Instances](instances.png)

---

## 🔹 Target Group

![Target Group](Target%20Group.png)

---

## 🔹 Security Group for ALB

![Security Group ALB](security%20group%20alb.png)

---

## 🔹 Security Group for EC2

![Security Group EC2](security%20group%20ec2-sg.png)

---

## 🔹 Application Output

![Output](output.png)

---

## 🔹 Final Output

![Final Output](output%201.png)

---

# ✅ Features

- High Availability
- Automatic Traffic Distribution
- Dynamic Scaling
- Fault Tolerance
- Better Performance
- Secure Infrastructure
- Load Management

---

# 📚 Learning Outcomes

Through this project, I learned:

- How to launch and configure EC2 instances
- How Application Load Balancer works
- How Auto Scaling automatically manages traffic
- How to configure Security Groups
- How Target Groups connect with Load Balancer
- Basics of scalable cloud infrastructure
- Real-time AWS deployment concepts

---

# 🚀 Future Improvements

- Add HTTPS support using SSL Certificate
- Configure CloudWatch Monitoring
- Add Route 53 Domain Mapping
- Implement CI/CD Pipeline
- Add Database Integration

---

# 🏁 Conclusion

This project successfully demonstrates scalable web application deployment on AWS using Application Load Balancer and Auto Scaling Group. The infrastructure efficiently handles traffic distribution and automatically scales resources based on demand, improving availability and reliability.


---

# 👩‍💻 Author

Akshata Naik

---
