# 80- SSL Certificates with ELB
## SSL/TLS Basic
- SSL cert is used to encrypt in-flight traffic between client and load balancer
- TLS is newer version of SSL- stands for transport layer security
- TLS is mainly used, but referred to as SSL many times
- Public SSL certs are issues by Certificate authorities
- SSL certs have an expiration date set by user and must be renewed

### How does it work?
- Traffic between user and LB is encrypted with cert (HTTPS)
- Traffic between LB and app is not encrypted (HTTP)
- Load balancers uses x.509 cert
- Certs can be managed using AWS Certificate Manager (ACM)
	- Or can also upload your own certs
- When creating HTTPS listener, must specify:
	- default cert
	- (optional) list of certs to support multiple domains
	- Clients can use Server Name Indication (SNI) to specific hostname they want ot reach
	- Can also specify security policy to support older versions of SSL/TLS (legacy clients)  

## SSL and Server Name Indication
- How do you load multiple SSL certs onto one web server so it can serve multiple websites?
- SNI is where the desired server name is indicated by the client
	- Specified in the initial SSL handshake
	- Server finds the correct certificate
- Only works for ALB, NLB, and CloudFront
- Does not work with CLB
[image](Pasted image 20240704153751.png)

## ELB Support for SSL certificates
- CLB only supports one SSL certificate
- ALB, NLB
	- Suports multiple listeners with multiple certificates using SNI