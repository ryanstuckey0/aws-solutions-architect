# 170- AWS Global Accelerator
## Problem
- Say we have an application w/ global users who want to access it
- Users outside of deployed region will have a lot of hops, adding latency to the request
- Can go through AWS to minimize latency

## Unicast vs. Anycast IP
- Unicast IP- one server holds one IP address, and client is routed to specific server
- Anycast IP- all servers hold same IP address, and client is routed to closest one
- Global accelerator uses Anycast IP

## Global Accelerator
- Uses AWS internal network to route to application
	- Instead of over public Internet
- Will route through closest edge location -> AWS private network -> resource in region
- 2 Anycast IP created for application
	- Sends traffic directly to edge location
	- Edge locations send traffic to application
- Works with Elastic IP, EC2 instances, ALB, NLB (public or private)
- Consistent performance
	- Intelligent routing to lowest latency and healthy region
	- No cache (since IP never changes)
	- Internal AWS network is more sturdy/reliable
- Performs health checks on application
	- Failover is less than 1 minute for unhealthy instances
- Security
	- Secure- only need to whitelist 2 IP
	- DDoS protection w/ AWS Shield

## Global Accelerator vs CloudFront
- Global accelerator 
	- doesn't cache
	- Useful for applications running over TCP or UDP
	- Good for non-HTTP use cases (like gaming over UDP, IoT, or VoIP)
	- Good for HTTP that require 
		- static IP address
		- deterministic, fast, regional failover
- CloudFront does
	- Useful for handling cacheable content (images and videos)
	- Requests for content fulfilled at edge locations
- Gl
- Both 
	- use edge locations
	- Integrate with Shield
	- 