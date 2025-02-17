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
![Screenshot 2025-02-16 072356](https://github.com/user-attachments/assets/53426715-c438-42f0-a8dd-bd7041f21644)
![Screenshot 2025-02-16 072413](https://github.com/user-attachments/assets/70b7cb89-8dd0-42d0-9be0-49623ce19279)
![Screenshot 2025-02-16 072439](https://github.com/user-attachments/assets/7f4169be-f742-43c7-8b48-f1297effcdf7)
![Screenshot 2025-02-16 072454](https://github.com/user-attachments/assets/5206fb32-a497-4b11-9eef-22e70eaf68db)
---
4. **Availability Zones:** The architecture leverages two Availability Zones to enhance system reliability and fault tolerance.
5. **Public Subnets:** Public subnets are utilized for critical infrastructure components, including the NAT Gateway and Application Load Balancer.
6. **Web Server Security:** Web servers, implemented as EC2 instances, are positioned within private subnets to enhance security.
7. **Internet Access for Private Subnets:** Instances located in both the private application and data subnets are permitted internet access via the NAT Gateway.
![Screenshot 2025-02-14 141326](https://github.com/user-attachments/assets/a00eed87-8160-4806-94c0-a3267ca82d76)
![Screenshot 2025-02-14 141341](https://github.com/user-attachments/assets/d31dc89d-6faf-4d0c-afa7-66c157b45fc6)
![Screenshot 2025-02-14 141404](https://github.com/user-attachments/assets/00b8cdfa-3525-45d0-ae4f-61acf3b642e4)
![Screenshot 2025-02-14 141436](https://github.com/user-attachments/assets/a1285f27-af21-42ed-9717-e0faf1ef9da1)
---
### **Compute and Scalability**

8. **Website Hosting:** The website is hosted on EC2 instances.
9. **Load Balancing:** An Application Load Balancer, along with a target group, has been employed to distribute web traffic evenly to an Auto Scaling Group of EC2 instances across multiple Availability Zones.
![Screenshot 2025-02-17 043241](https://github.com/user-attachments/assets/ff432a0d-4b56-450c-b629-37f6bfeca65d)
![Screenshot 2025-02-17 043259](https://github.com/user-attachments/assets/be141917-0cfa-4628-ba8f-ef5e8320f759)
![Screenshot 2025-02-17 043324](https://github.com/user-attachments/assets/b4a0061b-ad87-4a85-b38f-09f87202f941)
---
10. **Auto Scaling:** An Auto Scaling Group has been utilized to automatically manage EC2 instances, thereby ensuring website availability, scalability, fault tolerance, and elasticity.
![Screenshot 2025-02-17 043451](https://github.com/user-attachments/assets/7d9e8abc-60c1-4792-a283-27dd3434aecf)
![Screenshot 2025-02-17 043508](https://github.com/user-attachments/assets/e9480c64-dedb-4e51-b24a-086c9bb285d6)
---
### **Database Management**

11. **Amazon RDS:** A managed relational database service (Amazon RDS) is used to handle application data, ensuring high availability, security, and automatic backups.
![Screenshot 2025-02-16 072515](https://github.com/user-attachments/assets/57a46515-d77f-458e-8117-fc6e6cbd1a5e)
---
### **Security and Monitoring**

12. **Monitoring and Alerts:** Simple Notification Service (SNS) has been configured to provide alerts regarding activities within the Auto Scaling Group.
![Screenshot 2025-02-17 043419](https://github.com/user-attachments/assets/af5ec48d-4b68-45c0-ba55-75d79b476759)
---
### **Domain Name**
13. **Secure Communications:** Application communications are secured using AWS Certificate Manager.
14. **Domain Registration and DNS Configuration:** The domain name has been registered, and a DNS record has been established using Amazon Route 53.
![Screenshot 2025-02-17 043522](https://github.com/user-attachments/assets/4c423789-6e17-41ff-837f-3774c3b7cde2)

---
### **Outputs and Variables**
![Screenshot 2025-02-17 043541](https://github.com/user-attachments/assets/aa0cbe7e-23e9-499e-8f86-93f4e3c5bf5a)
![Screenshot 2025-02-17 043552](https://github.com/user-attachments/assets/afef31e8-c4dd-453e-9786-13727720d686)
![Screenshot 2025-02-17 043609](https://github.com/user-attachments/assets/19b55396-8c5a-41b2-a37f-6884457a85ab)
![Screenshot 2025-02-17 045246](https://github.com/user-attachments/assets/e6cd2538-a9ff-49ea-a022-9d66943e495e)

## **Terraform Apply**
![Screenshot 2025-02-17 060258](https://github.com/user-attachments/assets/a314a8bf-2598-4e27-b400-d7de250f2300)
![Screenshot 2025-02-17 060400](https://github.com/user-attachments/assets/df663462-7ce2-4862-b8f1-505606aebdd6)
![Screenshot 2025-02-17 060427](https://github.com/user-attachments/assets/9ed5d4fa-2c05-4ce8-8b1a-db19f4690b5d)

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




