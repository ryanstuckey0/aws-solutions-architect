# 164- CloudFront Overview
- Content delivery network (CDN)
- Improve read performance by caching website content at edge locations
- Made of 216 edge locations (aka Point of Presence)
- Implicit DDoS protection because app is world wide- integrates with Shield and AWS Web Application Firewall

## Origins
- S3 Buckets
	- Uses CloudFront Origin Access Control (OAC)
		- Replaces Origin Access Identity (OAI)
	- Can be used to upload files to S3 (ingres)
- Custom origin (HTTP)
	- ALB, EC2 instance, S3 website, any HTTP backend

## How does it work?
- Client makes request -> edge location -> in cache? 
	- If no- request resource -> cache in edge location -> back to client
	- If yes- back to client
![500](attachments/Pasted%20image%2020240718182302.png)

![500](attachments/Pasted%20image%2020240718183138.png)

## CloudFront vs S3 Cross-Region Replication
- CloudFront
	- Auto-works for global edge network
	- Files cached for TTL (~1 day)
	- Great for static content that is widely available
- S3 Cross Region Replication
	- Needs explicitly setup in each region
	- Newest files are ready almost immediately (no TTL)
	- Read only