# Project Title: AWS Static Website Deployment

## Overview

This project demonstrates the deployment of a static HTML web app on AWS, leveraging various services to ensure high availability, fault tolerance, and security. The project utilizes a VPC with public and private subnets across two availability zones. It employs an Internet Gateway, Security Groups, Nat Gateway, Bastion Host, and an Application Load Balancer (ALB) to create a robust and secure infrastructure.

## Project Components

1. **VPC Configuration**
   - Set up a VPC with public and private subnets spanning two availability zones.
   - Utilize an Internet Gateway to enable communication between instances in the VPC and the Internet.

2. **Security Groups**
   - Implement Security Groups for firewall rules to control inbound and outbound traffic.

3. **High Availability and Fault Tolerance**
   - Design the infrastructure across two Availability Zones to enhance high availability and fault tolerance.

4. **Key Resources Placement**
   - Place resources like Nat Gateway, Bastion Host, and the Application Load Balancer in public subnets.
   - Web servers and database servers are located in private subnets for enhanced security.

5. **EC2 Instance Connect Endpoint**
   - Use the EC2 Instance Connect Endpoint to facilitate secure connections to resources in both public and private subnets.

6. **Nat Gateway**
   - Allow instances in private subnets to access the internet through Nat Gateway.

7. **EC2 Instances**
   - Use EC2 Instances to host the static website.

8. **Auto Scaling Group**
   - Implement an Auto Scaling Group to dynamically create EC2 instances, ensuring high availability, scalability, fault tolerance, and elasticity.

9. **Application Load Balancer (ALB)**
   - Utilize ALB to distribute web traffic across the Auto Scaling Group of EC2 instances in multiple availability zones.

10. **Route 53**
    - Register a domain name and create a record set using Route 53.

11. **GitHub Integration**
    - Store web files on GitHub for version control and ease of deployment.

12. **Web App Deployment Script**
    - Use the provided deployment script to automate the installation of the web app on EC2 instances.
    
    ```bash
    #!/bin/bash
    sudo su
    yum update -y
    yum install -y httpd
    cd /var/www/html
    wget https://github.com/azeezsalu/mole-sit...
    unzip mole.zip
    cp -r /var/www/html/mole-main/* /var/www/html
    rm -rf mole.zip mole-main
    systemctl enable httpd
    systemctl start httpd
    ```

13. **AMI Creation**
    - Once the website is installed on the EC2 instance, use the EC2 instance to create an Amazon Machine Image (AMI) for easy replication.

## Setup Instructions

1. Clone the GitHub repository for the project.
2. Configure AWS resources as per the provided reference diagram.
3. Execute the deployment script on the EC2 instances to install the web app.
4. Use Route 53 to associate the domain name with the deployed website.
5. Monitor the system through AWS Console for scalability, fault tolerance, and overall health.

## Additional Resources
. AWS Documentation: EC2 User Guilds

## Conclusion

This project showcases the implementation of a robust and scalable architecture on AWS for hosting a static HTML web app. The combination of various AWS services ensures high availability, security, and ease of management.
