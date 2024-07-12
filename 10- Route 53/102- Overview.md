- Highly available, scalable, fully managed and authoritative DNS
	- Authoritative means the customer can update DNs records
- Also a domain registrar
- Can also check health of resources
- The only service that guarantees 100% availability
- 53- reference to DNS port

## Route 53 Records
- Each record contains
	- Domain/subdomain
	- Record type- A or AAAA
	- Value- IP address
	- Routing policy- how route 53 responds to queries
	- TTL- amount of time record gets cached at DNS resolvers
- Supports record types-
	- must know- A / AAAA / CNAME / NS
	- advanced- CAA / DS / MX/ NAPTR / PTR / SOA / TXT / SPF / SRV

## Record Types
- A- maps a hostname to IPv4
- AAAA- maps a hostname to IPv6
- CNAME- maps a hostname to another hostname
	- Target is a domain name which must have a A or AAAA record
	- Cannot create CNAME record for top node of DNS namespace
		- i.e., can't create for example.com, but can for www.example.com
- NS- name servers for hosted zone
	- DNS names/IP addresses that respond to DNS queries

## Hosted Zones
- Container of records that define how to route traffic to domain and subdomain
- Public hosted zone- contains records that specify how to route traffic on Internet
- Private hosted zone- contains records that specify how you route traffic within one or more VPCs (private domain name)
- Cost- $0.50 per month per hosted zone
- Cost- Domain name is $12/year

## Public vs. Private Hosted Zone
![](attachments/Pasted%20image%2020240706100122.png)

