![Alt text](Terraform-Ecommerce-Architecture.jpg)


---

# Dynamic Website Deployment on AWS Using Terraform

## Project Overview

This project involves hosting a dynamic website on Amazon Web Services (AWS) as part of a DevOps initiative, utilizing Terraform for the provisioning of infrastructure. A GitHub repository containing the reference diagram and deployment scripts has been created.

---
## Architecture and Configuration

### **Networking and Security**

1. **Virtual Private Cloud (VPC):** The infrastructure includes a configured VPC with both public and private subnets spanning two availability zones.
![Screenshot 2025-02-14 121712](https://github.com/user-attachments/assets/8f392c65-d2c1-4baf-b1f0-82f4b0fde850)
![Screenshot 2025-02-14 121801](https://github.com/user-attachments/assets/a9409a41-e645-4f1f-bf74-3a87a5e475f6)
![Screenshot 2025-02-14 121815](https://github.com/user-attachments/assets/ddffa296-8e1d-409c-8d84-380c7fd5a2a5)
![Screenshot 2025-02-14 121835](https://github.com/user-attachments/assets/c3e76dd7-5faa-4d0a-8174-1043db7fc2d2)
---
2. **Internet Gateway:** An Internet Gateway has been deployed to facilitate connectivity between the VPC instances and the broader internet.
![Screenshot 2025-02-14 121712](https://github.com/user-attachments/assets/ed5b8b5d-189d-4ccc-a445-123b708b1462)
---
3. **Security Groups:** Security Groups have been established to function as a network firewall mechanism.
4. **Availability Zones:** The architecture leverages two Availability Zones to enhance system reliability and fault tolerance.
5. **Public Subnets:** Public subnets are utilized for critical infrastructure components, including the NAT Gateway and Application Load Balancer.
6. **EC2 Instance Connect Endpoint:** An EC2 Instance Connect Endpoint has been implemented to ensure secure connections to resources located within both public and private subnets.
7. **Web Server Security:** Web servers, implemented as EC2 instances, are positioned within private subnets to enhance security.
8. **Internet Access for Private Subnets:** Instances located in both the private application and data subnets are permitted internet access via the NAT Gateway.
![Screenshot 2025-02-14 141326](https://github.com/user-attachments/assets/a00eed87-8160-4806-94c0-a3267ca82d76)
![Screenshot 2025-02-14 141341](https://github.com/user-attachments/assets/d31dc89d-6faf-4d0c-afa7-66c157b45fc6)
![Screenshot 2025-02-14 141404](https://github.com/user-attachments/assets/00b8cdfa-3525-45d0-ae4f-61acf3b642e4)
![Screenshot 2025-02-14 141436](https://github.com/user-attachments/assets/a1285f27-af21-42ed-9717-e0faf1ef9da1)
---
### **Compute and Scalability**

9. **Website Hosting:** The website is hosted on EC2 instances.
10. **Load Balancing:** An Application Load Balancer, along with a target group, has been employed to distribute web traffic evenly to an Auto Scaling Group of EC2 instances across multiple Availability Zones.
11. **Auto Scaling:** An Auto Scaling Group has been utilized to automatically manage EC2 instances, thereby ensuring website availability, scalability, fault tolerance, and elasticity.

### **Database Management**

12. **Amazon RDS:** A managed relational database service (Amazon RDS) is used to handle application data, ensuring high availability, security, and automatic backups.

### **Security and Monitoring**

13. **Secure Communications:** Application communications are secured using AWS Certificate Manager.
14. **Monitoring and Alerts:** Simple Notification Service (SNS) has been configured to provide alerts regarding activities within the Auto Scaling Group.

### **Domain Name**

15. **Domain Registration and DNS Configuration:** The domain name has been registered, and a DNS record has been established using Amazon Route 53.

---

## Deployment Instructions

1. Clone the GitHub repository:
   ```sh
   git clone <repository-url>
   cd <project-directory>
   ```
2. Deploy the Terraform scripts to set up the infrastructure.
3. Configure DNS settings in Route 53 to point to the ALB.
4. Upload the application code to S3 and deploy it to EC2 instances.
5. Validate the deployment by accessing the website using the registered domain name.

## Monitoring and Alerts

- The Auto Scaling Group is configured with SNS to send notifications on instance scaling events.
- AWS CloudWatch can be used for monitoring instance performance and logging application errors.

## Conclusion

This project demonstrates a highly available, scalable, and secure architecture for hosting a dynamic website on AWS using best DevOps practices. By leveraging AWS services, we ensure seamless scalability, security, and efficient resource management.




