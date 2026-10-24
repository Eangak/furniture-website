Furniture Website — Docker Swarm & AWS CI/CD Project
Project Overview

The Furniture Website is a web application designed to showcase furniture products through a user-friendly website. This project also demonstrates how to build, containerize, deploy, and manage a web application using modern DevOps and cloud technologies.

The application source code is maintained in GitHub, while Jenkins automates the CI/CD workflow. Docker packages the website into a container image, Amazon Elastic Container Registry (Amazon ECR) stores the image, and Docker Swarm deploys and manages the application across multiple AWS EC2 instances.

The project provides practical experience with source-code management, automated deployment, container orchestration, cloud infrastructure, and website accessibility.

🎯 Project Objectives

Develop and maintain a furniture website.

Store and manage application source code in GitHub.

Automate the build and deployment process using Jenkins.

Build Docker images to package the website and its dependencies.

Push versioned Docker images to Amazon ECR.

Deploy and manage the application using Docker Swarm.

Run multiple replicas across a manager and worker nodes.

Practice deployment verification, version management, and rollback procedures.

Explore Cloudflare for secure and convenient access to web services, where configured.

🏗️ System Architecture

The deployment workflow follows this sequence:

Developer: Updates the website source code.

GitHub: Stores the source code and deployment files.

Jenkins: Runs the pipeline to build and publish the Docker image.

Docker: Packages the website into a versioned image.

Amazon ECR: Stores the published image.

Docker Swarm Manager: Deploys the selected image as a stack or service.

Swarm Workers: Run application replicas according to the service configuration.

Website Users: Access the published website through the configured endpoint.

🔄 CI/CD Workflow

The intended pipeline workflow is:

Select an image version in Jenkins.

Retrieve the website source code from GitHub.

Build the Docker image.

Authenticate to Amazon ECR.

Push the image to the ECR repository.

Prepare the Docker Stack configuration.

Deploy the application to Docker Swarm.

Verify the deployment and service replicas.

Use a defined rollback procedure if a deployment needs to be reversed.

🐳 Docker Swarm Deployment

The application runs as a Swarm service on AWS EC2 instances. The Swarm manager controls service deployment, while worker nodes can run application replicas.

The deployment configuration is maintained in docker-stack.yml. It defines the container image, published port, overlay network, replica count, and service update settings.

The service can be inspected using:

docker node ls
docker service ls
docker service ps furniture_furniture-website

☁️ AWS Container Registry

Amazon ECR is used as the private container image registry.

Example image naming format:

254209146027.dkr.ecr.us-east-1.amazonaws.com/furniture-website:<version>

Replace <version> with the actual image tag selected for the deployment.

🏗️ System Architecture

The deployment workflow follows this sequence:

Developer: Updates the website source code.

GitHub: Stores the source code and deployment files.

Jenkins: Runs the pipeline to build and publish the Docker image.

Docker: Packages the website into a versioned image.

Amazon ECR: Stores the published image.

Docker Swarm Manager: Deploys the selected image as a stack or service.

Swarm Workers: Run application replicas according to the service configuration.

Website Users: Access the published website through the configured endpoint.

🔄 CI/CD Workflow

The intended pipeline workflow is:

Select an image version in Jenkins.

Retrieve the website source code from GitHub.

Build the Docker image.

Authenticate to Amazon ECR.

Push the image to the ECR repository.

Prepare the Docker Stack configuration.

Deploy the application to Docker Swarm.

Verify the deployment and service replicas.

Use a defined rollback procedure if a deployment needs to be reversed.

🐳 Docker Swarm Deployment

The application runs as a Swarm service on AWS EC2 instances. The Swarm manager controls service deployment, while worker nodes can run application replicas.

The deployment configuration is maintained in docker-stack.yml. It defines the container image, published port, overlay network, replica count, and service update settings.

The service can be inspected using:

docker node ls
docker service ls
docker service ps furniture_furniture-website

☁️ AWS Container Registry

Amazon ECR is used as the private container image registry.

Example image naming format:

254209146027.dkr.ecr.us-east-1.amazonaws.com/furniture-website:<version>

Replace <version> with the actual image tag selected for the deployment.
