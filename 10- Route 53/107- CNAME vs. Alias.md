# 107- CNAME vs. Alias
- AWS resource (LB, CloudFront, etc.) exposes AWS hostname
- Sometimes we want to map that hostname to our own custom hostname
- CNAME- used to point hostname to any other hostname
	- ex: myhostname.domain.com => myhostname2.domain2.com
	- Works for non root domain (i.e., works for myhostname.domain.com but not for domain.com)
- Alias- specific to Route 53, allows you to point hostname to specific AWS resource
	- Works for root domain and non root domain
	- Free to use
	- Health check built in

## Alias Records
- Only mapped to resources
- Auto updates if resource IP address changes
- Can be used for top node of DNS namespace (Zone Apex)
- Alias record- always type A or AAAA
- TTL is set automatically

## Alias Records Targets
- ELB, CloudFront, API Gateway, Elastic Beanstalk, S3 Websites, VPS interface, Global Accelerator, Route 53 record in same hoted zone
- **Not EC2 DNS name**
- When creating alias, set record type, check alias toggle, select resource type, region, and then resource instance