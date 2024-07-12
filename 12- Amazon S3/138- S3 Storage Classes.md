# 138- S3 Storage Classes
- Standard- General Purpose
- Standard- Infrequent Access (IFA)
- One-Zone- Infrequent Access
- Glacier Instant Retrieval
- Glacier Flexible Retrieval
- Glacier Deep Archive
- Intelligent Tiering

- Can move objects between classes manually or with lifecycle configurations

## S3 Durability and Availability
- Durability- represents how many times an object will be lost by Amazon S3
	- has 11 9's of durability- 99.99999999999%
	- meaning if we store 10,000,000 objects, we will only lose 1 single object every 10,000 years
- Availability- measures how readily a service is
	- Depends on storage class
	- For example- S3 Standard has 99.99% availability- unavailable for only 53 minutes per year

## S3 Standard- General Purpose
- 99.99% availability
- Used for frequently accessed data
- low latency
- Can sustain 2 concurrent facility failures
- Good for big data analytics, mobile gaming, content distribution

## S3- Infrequent Access
- Less frequent, but can still access rapidly when needed
- Standard- IA- 99.9% availability
	- good for data backups, recovery
- One-Zone- IA- 99.5% availability, 9 9's durability, all data lost if AZ destroyed
	- Use case: secondary backups, or data that can be recreated

## S3 Glacier
- Pay for storage, and for retrieval
- 3 classes
	- Instant retrieval
		- Access within milliseconds, minimum storage duration of 90 days
	- Flexible retrieval
		- Three options for retrieving data- expedited (1 to 5 mintues), standard (3 to 5 hours), bulk (5 to 12 hours; free)
		- minimum storage duration of 90 days
	- Deep archive
		- long term storage
		- two tiers retrieval- Standard- 12 hours, bulk 48 hours
		- minimum storage durations of 180 days

## S3 Intelligent Tiering
- small monthly monitoring and auto-tiering fee
- moves objecs automatically between tiers based on usage
- No retrieval charges
- A couple tiers:
	- Frequent access- default
	- Infrequent access- not accessed for 30 days
	- Archive instant access- not accessed for 90 days
	- Archive access (optional)- configurable from 90-700 days
	- Deep archive access (optional) configurable from 180-700 days

## Storage Class Comparison
- no need to memorize
![](attachments/Pasted%20image%2020240711233136.png)
## Pricing Comparison
- no need to memorize
- varies by region 
![](attachments/Pasted%20image%2020240711233153.png)