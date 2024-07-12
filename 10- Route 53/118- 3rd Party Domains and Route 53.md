# 118- 3rd Party Domains and Route 53
- can buy domain name with any domain registrar you want by paying annual name
- Domain registrar will typically also provide DNS service to manage DNS records
- You can also choose another DNS service to manage DNS records
- So, let's say you get domain name on GoDaddy
	- Create public hosted zone in Amazon Route53
	- Edit GoDaddy to point to Amazon Route 53 nameservers
- Domain registrar != DNS service