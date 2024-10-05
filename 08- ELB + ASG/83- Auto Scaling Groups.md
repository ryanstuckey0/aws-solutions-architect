# 83- Auto Scaling Groups
- Load can change overtime in real world
- Auto scaling group (ASG)- scales out by adding EC2 instances for increased load, or vice versa
- Can define settings to control minimum and maximum number of instances
- Will auto-register new EC2 instances to load balancer
- Will also re-create new instance if previous one is unhealthy
- ELB health check gets passed onto ASG so it can handle termination/creation of instances
- Launch template will contain info for ASG on how to launch instances 
	- has things like AMI, instance type, user data, security groups, etc.
- Define min, max, initial, and scaling policies

## Cloud Watch
- can scale in and out based on cloud watch alarms
- Alarms can be triggered by any metric you want