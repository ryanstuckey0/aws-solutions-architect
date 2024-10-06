# 200- Docker Introduction
- Can take advantage of Docker's containerized "run-anyway" capability to deploy apps to AWS
- Use cases- microservice architecture, lift and shift
- Docker agent runs on servers, handles starting Docker containers
- Docker images are stored in Docker repo
	- Main one is Docker Hub
	- Amazon also offers ECR- Elastic Container Registry
		- Offers both private and public options
- How does Docker differ from a virtual machine?
	- Resources are shared w/ a host- many containers on one server ![](attachments/Pasted%20image%2020241006085318.png)
	- Less secure as containers can share resources, networking, etc.
- Dockerfile defines how container will look- includes base Docker image, and files to run app
	- Builds a Dockerimage, which we can then push to repositories

## Docker containers on AWS
- Amazon Elastic Container Service (ECS)
- Amazon Elastic Kubernetes Service (EKS)
	- based on open source Kubernetes (k8s)
- AWS Fargate
	- Serverless, works with ECS or EKS
- Amazon Elastic Container Registry (ECR)
- 