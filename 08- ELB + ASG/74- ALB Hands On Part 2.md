# Network Security
- with previous setup, we could access EC2 instance through its own IP, and through the LB IP
- can edit security group to just allow traffic from the load balancers security group
- Can also add rules for each listener (hostname, path, header, etc.)
	- listener is a combination of protocol + port
	- need to select action when the specific rule is triggered- can forward to target group, redirect to URL, or return fixed response
	- Also set priority of rule (1-50000)