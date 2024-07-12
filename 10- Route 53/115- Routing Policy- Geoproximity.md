- Route traffic to resources based on geographic location of users and resources
- Shift more traffic to resources based on define bias
	- Expand bias to send more traffic to resource (1-99)
	- Or decrease to send less traffic (-1- -99)
- Resources can be
	- AWS Resource (specify region)
	- Non-AWS resource (specify latitude and longitude)
- Need to use Route 53 traffic flow (advanced feature)

## Examples
- with zero bias, resources are perfectly divided: ![](attachments/Pasted%20image%2020240706141008.png)
- but when we increase bias on 1 resource, more traffic is routed there ![](attachments/Pasted%20image%2020240706141112.png)

