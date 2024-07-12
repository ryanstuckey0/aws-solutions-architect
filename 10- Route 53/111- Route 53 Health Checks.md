# 111- Route 53 Health Checks
- HTTP health checks used for only public resources
- Create health checks from route 53 to resource (e.g., ALB0)
- Health checks will allow automated DNS failover
- Three health check tyeps
	1. Monitor endpoint- application, server, etc.
	2. Monitor other health checks
	3. Monitor CloudWatch alarms (most control/customization)
- Integrated with CloudWatch metrics

## Monitor an Endpoint
- 15 global health checkers check endpoint
	- Can set health/unhealthy threshold
	- Set interval
	- Supports HTTP, HTTPS, TCP
- Considered health with 2xx and 3xx return codes
- Can also be setup to read first 5120 bytes of response
- Need to configure route/firewall/security group to allow incoming requests from Route 53 health check IP address range

## Calculated Health Checks
- Combine results of multiple health checks into single health check
- Can use OR/AND/NOT between health checks
- Combine up to 256 health checks
- Specify how many children health checks need to pass to make parent passed
- Can perform maintenance on underlying resources w/o causing health check to fail

## CloudWatch Alarm Health Checks
- Route 53 health checks live outside VPC
- Q: So how can we run health checks on private resources (within VPC)
- A: Create CloudWatch alarms to monitor health checks within VPC
- Route 53 Health Check -> CloudWatch alarm -> CloudWatch metric -> private resource