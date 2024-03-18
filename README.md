# 🚀 Cloud Native Monitoring App Deployment 📊

## Introduction
The application provides real-time monitoring of resource utilization within the cloud environment. It displays memory and CPU usage metrics of the hosting instance. This enables proactive management and optimization of resource allocation, ensuring optimal performance and availability of services.

## Prerequisites
Before you begin, ensure you have the following prerequisites in place:
- Visual Studio Code (or any preferred code editor) 💻
- AWS Account ☁️
- Cloud9 Instance (Optional) or configured AWS CLI ☁️
- Docker 🐳
- kubectl ☸️
- Python 3 🐍

## Step-by-Step Guide
### 1. Setup Environment
- Configure your AWS credentials either through AWS CLI or by setting up a Cloud9 instance in your AWS account.
- Install Docker on your local machine.
- Install kubectl to interact with your Kubernetes cluster.
- Ensure Python 3 is installed on your system.

### 2. Push Docker Image to AWS ECR
- Build your Docker image for the monitoring application:
  ```bash
  docker build -t monitoring-app .


- Tag your Docker image with your AWS ECR repository URI:
  ```bash
  docker tag monitoring-app:latest <your-ecr-repository-uri>/monitoring-app:latest

- Push your Docker image to your AWS ECR repository:
  ```bash
  docker push <your-ecr-repository-uri>/monitoring-app:latest
### 3. Create Kubernetes Cluster and Node Group
- Create an EKS cluster using the AWS Management Console or AWS CLI.
- Configure your Cloud9 instance with kubectl to interact with your EKS cluster.
- Create a node group containing 2 t2.micro instances to serve as worker nodes for your cluster.

  ### 4. Manage Services and Deployments using Python
- Update the URI of the Docker image in the eks.py file with your ECR repository URI.
- Run the Python script to create deployments and services:
  ```bash
  python3 eks.py

### 5. Accessing the Application
- Once deployed, forward the application to your localhost using kubectl port-forward:
  ```bash
  kubectl port-forward svc/my-flask-service -p 5000:5000
Now, you can access your cloud-native monitoring application by navigating to http://localhost:5000 in your web browser.
## Challenges Faced

During the deployment process, challenges were encountered in configuring AWS services, managing Kubernetes resources, and integrating Python scripts for managing deployments and services. These challenges were overcome by referring to AWS documentation, Kubernetes documentation, and seeking assistance from community forums.

## Key Takeaways

- Understanding the deployment process for cloud-native applications on AWS EKS.
- Leveraging Python scripts for managing Kubernetes resources provides automation and flexibility in deployment workflows.
- Hands-on experience with Docker, Kubernetes, and AWS services enhances proficiency in cloud-native development and deployment.

## Resources

- [AWS Documentation](https://docs.aws.amazon.com/) 📚
- [Docker Documentation](https://docs.docker.com/) 🐳
- [Kubernetes Documentation](https://kubernetes.io/docs/) ☸️

