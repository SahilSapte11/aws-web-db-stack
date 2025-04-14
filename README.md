# AWS Web-DB Stack 🚀

This project provides an automated AWS infrastructure setup using **Infrastructure as Code (IaC)** via **AWS CloudFormation**. It sets up a scalable, highly available cloud architecture including:

- ✅ A Virtual Private Cloud (VPC)
- ✅ Public and private subnets
- ✅ EC2 Web Server with Load Balancer and Auto Scaling
- ✅ Private Database Server
- ✅ Private File Server and DNS Server
- ✅ Internet and NAT Gateway for routing

---

## 📁 Project Structure

```
aws-web-db-stack/
├── templates/
│   └── main.yaml         # CloudFormation template
├── README.md             # Project documentation
├── .gitignore            # Git ignore file
```

---

## 🚦 What It Deploys

| Component         | Description                                |
|------------------|--------------------------------------------|
| VPC              | Custom VPC with public & private subnets   |
| Subnets          | 1 Public Subnet, 1 Private Subnet          |
| Web Server       | EC2 instance in public subnet              |
| Load Balancer    | Application Load Balancer in front of web server |
| Auto Scaling     | Auto Scaling Group for high availability   |
| DB Server        | EC2 instance in private subnet             |
| File/DNS Server  | EC2 instance in private subnet             |
| Security Groups  | For Web, DB, and Internal servers          |
| Routing          | Internet Gateway for public, NAT for private |

---

## 🚀 How to Deploy

> Prerequisites:
> - AWS CLI configured
> - A valid EC2 Key Pair
> - AMI ID for EC2 (Amazon Linux 2 recommended)

### 🔧 Deploy with AWS CLI

```bash
aws cloudformation create-stack \
  --stack-name aws-web-db-stack \
  --template-body file://templates/main.yaml \
  --parameters ParameterKey=KeyName,ParameterValue=YourKeyName \
               ParameterKey=AmiId,ParameterValue=ami-xxxxxxxxxxxxxxxxx \
  --capabilities CAPABILITY_NAMED_IAM
```

---

## 🛠️ Customize

You can customize:
- CIDR blocks for VPC and subnets
- Instance types
- AMI IDs
- Additional user data scripts (e.g., to install web server or DB)

---

## 📷 Screenshots (Optional)

You can add screenshots of:
- EC2 Dashboard
- Load Balancer setup
- VPC architecture diagram (from AWS console)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙌 Acknowledgments

- AWS Docs
- CloudFormation Templates Reference
- Inspiration from real-world cloud deployments

---

## 👨‍💻 Author

**Sahil Sapte**  
📧 [LinkedIn](https://www.linkedin.com/in/sahilsapte/) • 🌐 GitHub: [SahilSapte11](https://github.com/SahilSapte11)
