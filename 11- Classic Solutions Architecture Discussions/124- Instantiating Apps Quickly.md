# 124- Instantiating Apps Quickly
- How we launch a full stack (EBS, RDS, ELB, EC2) quickly?
- For EC2 instances- we can use Golden AMI- everything (OS, dependencies, apps) are all installed beforehand
	- Also bootstrap instance via user data
	- Use Golden AMI and user data together (similar to elastic Beanstalk)
- RDS- restore from snapshot when scaling
- EBS- also restore from snapshot
- 