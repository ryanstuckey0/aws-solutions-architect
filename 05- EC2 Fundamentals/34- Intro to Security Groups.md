- Control how traffic is allowed into and out of EC2 instances
- Rules can be referenced using IP address or other security groups
- Only contain **allow** rules
- Security groups act as firewall to EC2 instances
- Regulate the following
	- Open ports
	- Authorized IP ranges
	- Control of inbound network
	- Control of outbound network
- Security groups can be attached to multiple instances
- Locked to region/VPC combination
- Security groups operate outside EC2 instance (i.e., EC2 instance won't know if traffic is. blocked)
- If application is not accessible due to
	- Timeout- means security group has blocked traffic
	- Connection refused- mean it is an application error (within EC2 instance)
- By default
	- All inbound traffic is blocked
	- All outbound traffic is allowed
## Referencing security groups from other security groups
- Attaching security groups to an EC2 instance can allow those instances to connect to other EC2 instance with those groups also attached
	- Means we don't have to think about IPs, just security groups
	  [image](Pasted image 20240619102618.png)

## Ports to Know
- 22 = SSH (secure shell)
- 21 = FTP (file transfer protocol)
- 22 = SFTP (secure file transfer protocol)
- 80 = HTTP (hypertext transfer protocol)
- 443 = HTTPS (hypertext transfer protocol secure)
- 3380 = RDP (remote desktop protocol) (windows)
- 