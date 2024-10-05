# 85- Auto Scaling Policies
- Dynamic scaling
	-  target tracking scaling
		- Define a target value for some metric, and then ASG scales to keep metric around that target value
	- Simple/Step Scaling
		- Define CloudWatch alarm on metric to scale in/out
- Scheduled scaling
	- Schedule scaling based on date/time
- Predictive scaling
	- learn/analyze load and then schedule scaling based on forecast

## Good metrics to scale on
- CPU utilization- average across all instances
- Request count per target- number of instances hitting targets
- Network I/O- if application is network bound
- Or custom metrics setup in CloudWatch

## Scaling Cooldowns
- In cooldown period after scaling in/out- defaults to 300 seconds
- Waits for metrics to stabilize before ASG does any more scaling
- Use a ready-to-use AMI to reduce configuration time for EC2 instances
	- Means scaling happens faster, more responsive
- 