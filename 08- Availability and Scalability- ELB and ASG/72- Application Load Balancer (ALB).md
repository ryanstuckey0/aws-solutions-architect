- Works on network layer 7 (HTTP)
- Load balances to multiple HTTP applications across machines, or withint eh same machine
- Support for HTTP/2 and WebSocket
- Supports redirects (from HTTP to HTTPS for example)
- Can route requests to different target groups based on 
	- paths in URL 
	- hostname of URL
	- query string
	- headers (implies can then route on protocol, IP address, etc.)
- Great for containerized services
- Has port mapping to redirect to dynamic port on EC2

## Target groups
- Can be EC2 instances (could be managed by auto scaling group)- HTTP
- ECS tasks- HTTP
- Lambda functions- HTTP request translated into JSON event
- IP addresses

- Can also route to multiple target groups

## Good to know
- ELB has a fixed hostname
- Application servers don't see IP of client directly
	- IP is in header under key X-Forwarded-For
	- Port is in X-Forwarded-Port
	- Protocol is in X-Forwarded-Proto
- Client talks with load balancer, terminates connection, then load balancer talks to EC2 instance
	- Connection from client is terminated at ALB