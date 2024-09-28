
# Deploy a Highly Available Website with Terraform on AWS

This project demonstrates deploying a highly available website on AWS using Terraform to manage the infrastructure. The setup consists of EC2 instances serving a custom PHP website, and traffic is distributed using an Elastic Load Balancer (ELB) for high availability.

---

## 📝 Project Overview

- **Website**: Custom PHP-based website displaying instance IDs.
- **Infrastructure**: Public and private subnets, EC2 instances, and an ELB.
- **Automation**: Infrastructure as Code (IaC) with Terraform.

### Key Components:
- **EC2 Instances**: Apache web servers configured to serve the website.
- **Elastic Load Balancer**: Distributes traffic across EC2 instances for high availability.
- **Security Groups**: Control inbound and outbound traffic for the instances and ELB.
- **Terraform**: Declaratively manages AWS resources for automation and scalability.

---

## 📂 Project Structure

- **`main.tf`**: Configures EC2 instances and user data for server initialization.
- **`networking.tf`**: Sets up VPC, subnets, and routes.
- **`security.tf`**: Defines security groups for EC2 instances and ELB.
- **`load_balancer.tf`**: Configures the Elastic Load Balancer for traffic distribution.
- **`outputs.tf`**: Outputs ELB DNS for accessing the deployed website.

---

## ⚙️ Pre-requisites

Ensure you have the following before proceeding:

- **AWS Account** with permissions for EC2, ELB, and VPC services.
- **Terraform Installed**: [Download Terraform](https://www.terraform.io/downloads).
- **AWS CLI Configured** with credentials for your AWS account.

---

## 🚀 How to Use

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Aml286/Deploy-a-Highly-Available-Website-with-Terraform-on-AWS.git

### 2️⃣ Initialize Terraform

terraform init
### 3️⃣ Apply the Terraform Configuration
Run the following to deploy the infrastructure:

terraform apply
This will deploy the EC2 instances in private subnets.

It configures the Apache web server to serve the custom PHP website.
The public subnets, security groups, and ELB will also be set up.
### 4️⃣ Access the Website
To get the DNS address of the website, run:

terraform output site_address
Visit the website using the outputted DNS address of the ELB.

### 5️⃣ Test High Availability
To test the availability and load balancing, continuously send HTTP requests:

watch curl -s $(terraform output site_address)
### 6️⃣ Destroy Resources
To tear down the infrastructure:

terraform destroy
If you want to destroy specific resources (e.g., the ELB security group):

terraform destroy -target=aws_security_group.elb_sg
📊 Conclusion
This project shows how to deploy a highly available and scalable website on AWS using Terraform. The infrastructure automation provided by Terraform makes resource management, updates, and decommissioning efficient and straightforward.

Before completing the Lab instructions, the environment will look as follows:

![before ELB](https://github.com/user-attachments/assets/a5c67833-53d6-413e-8914-a7eede433f44)

After completing the Lab instructions, the environment should look similar to:

![after elb](https://github.com/Aml286/Deploy-a-Highly-Available-Website-with-Terraform-on-AWS/blob/main/after%20elb.png)
