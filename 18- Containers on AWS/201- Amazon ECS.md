# 201- Amazon ECS
## EC2 Launch Type
- ECS = elastic container service
- EC2 Launch Types is the type of ECS Cluster
	- You must provision and maintain the infra (EC2 instances) that make up the ECS
- Each EC2 instance runs the ECS agent to register w/ the ECS cluster
	- AWS will then take care of starting/stoping containers

## Fargate Launch Type
- Serverless way to launch containers on AWS
- You do not provisino/maintain infra
- Create task definitions- then AWS runs ECS tasks for you based on the CPU/RAM needs
- To scale, just increase number of tasks

## IAM Roles For ECS
- EC2 instance profile- applies only to EC2 launch types
	- Used by ECS agent for the following tasks
		- Make API calls to ECS service
		- Send logs to CloudWatch
		- Pull Docker images from ECI
		- Retrieve secrets from Secrets Manager or SSM Parameter Store
- ECS Task Roles
	- Each task can have its own specific roles
	- Each role can be linked to different ECS service based on what that task does
	- Task role is defined in task definition

## Load Balancer Integrations
- Expose tasks (not containers) to load balancers
- Can use an ALB- supports most use cases
- NLB- useful for high throughput, high performance, or w/ AWS Private Link
- CLB- supported but not recommend (doesn't work w/ Fargate)

## Data Persistance
### EFS Data Volume
- Can mount EFS onto ECS cluster
- Works w/ both EC2 and Fargate Launch Types
- Tasks running in any AZ will share same data via EFS file system
- Using Fargate + EFS = Serverless
- **S3 cannot be mounted as a filesystem on ECS Tasks)**
