# 101- What is a DNS?
- DNS- domain name server
- Translates human friendly hostnames into IP addresses
- Uses hierarchical name structure
- Terminology
	- Domain registrar- Amazon Route 53, GoDaddy, etc.
	- DNS records- A, AAAA, CNAME, NS
	- Zone file- contains DNs records
	- Name server- resolves DNS queries (authoritative or non-authoritative)
	- Top level domain (TLD)- .com, .us, .in
	- Second level domain (SLD)- amazon.com, google.com, etc.

![](url-example.png)

## How DNS works
- web browser asks local DNS server used for lookups 
- Local DNS will ask Root DNS- DNS returns what it knows about URL (maybe just TLD)
	- Root DNS managed by ICANN
- Request moves onto TLD DNS server and can return full IP; might not know exact location, but can point to location where the exact location can be found
	- Managed by IANA (branch of ICANN)
- Request can finally move onto SLD DNS
	- Managed by domain Registrar (e.g., Amazon Registrar)
- Local DNS will then cache the IP address for that URL
- Web browser will then use the IP to access the server