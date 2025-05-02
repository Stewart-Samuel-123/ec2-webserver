# EC2 Web Server Deployment

This project demonstrates how to deploy a basic Apache web server on an AWS EC2 instance using a user data script.

---

## 🔧 What I Did

- Launched a t2.micro EC2 instance using AWS Free Tier
- Used a Bash script in the **user data** section to:
  - Update the system
  - Install Apache (httpd)
  - Start and enable the Apache service
  - Serve a simple web page

---

## 💻 Script Used

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello from EC2</h1>" > /var/www/html/index.html
