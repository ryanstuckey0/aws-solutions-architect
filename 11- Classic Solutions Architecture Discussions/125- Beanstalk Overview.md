# 125- Beanstalk Overview
- Difficult to reconfigure infrastructure every time
- Many applications will have similar architecture

## Overview
- Developer centric way to deploy application on AWS
- Managed service that deploys all necessary apps for you
- Deploys app, scaling, load balancing, database
- App code is only responsibility of developer
- Free to use- just pay for underlying services

## Components
- Application
- Application version
- Environment
	- Collection of AWS env
	- Tiers- web server env and worker env
	- Can have multiple envs (dev, test, prod)
	![](attachments/Pasted%20image%2020240711192203.png)

## Supported platforms
- Many- Go, Java, Docker, .NET, etc.

## Worker Tier vs. Worker Tier
- Web env- Route 53, ELB, ASG, EC2
- Worker env- SQS queue, SQS messages, ASG, EC2, scale based on number of messages
	- Can push messages from web env to worker env
## Deployment Modes
- Single instance- great for dev, elastic IP -> EC2 instance
- High availability- great for prod, ALB -> ASG -> EC2 -> RDS, multi-AZ