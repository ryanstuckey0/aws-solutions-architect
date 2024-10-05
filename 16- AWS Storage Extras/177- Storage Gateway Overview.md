# 177- Storage Gateway Overview
- AWS is pushing for hybrid cloud
- Could be due to a couple different reasons
	- Lots of things to migrate
	- Security req's
- Problem- S3 is proprietary technology, so how can we utilize this in on-prem applications
- Solution- AWS storage gateway
- Gateway gets installed in on-prem datacenter

## AWS Storage Gateway
- Bridges on-prem data to cloud data
- Use cases
	- Distaster recovery
	- Tiered storage (cold data in cloud, warm data on-prem)
	- Store main data in S3, cache in on-prem env
- Types of Storage Gateway
	- S3
	- FSx
	- Volume
	- Tape

## S3 File Gateway
- Given an S3 bucket (any storage class except glacier)
- We want to connect the S3 bucket to on-prem server using a standard file system
- Using the S3 File Gateway, it will convert normal requests from the on-prem server to HTTP requests to the S3 bucket
- Can then make a lifecycle policy to archive objects into Glacier
- Bucket will be accessible via NFS and SMB protocol
- Need to create IAM roles for each File Gateway
- If using SMB, can also integrate with AD for user authentication

## FSx File Gateway
- Allows access to FSx for Windows File Server
- But if FSx for Windows File Server is already natively compatible w/ on-prem server, why do we need a file gateway?
- A file gateway enables us to have a local cache in the file gateway
- Also includes native Windows compatibility- NFTS, SMB, AD

## Volume Gateway
- Block storage using iSCS protocol backed by S3
- Creates snapshots of EBS volumes and backs them up to S3
- Cached volumes - provides low latency access to recent data
- Stored volumes- entire dataset stays on-prem, scheduled backup to S3

## Tape Gateway
- Useful for companies that have a tape backup system
- Virtual Tape Library (VTL) is backed by S3 and Glacier
- Backs up data using tape-based processed + iSCSI interface
- Also works with backup software vendors

## Hardware Applicance
- Normally, storage gateway can run in VM in on-prem DC
	- Can also host in EC2 in AWS (lose some caching benefits w/ S3 File Gateway)
- If this is not possible, you can buy a Storage Gateway Hardware Applicance
- Works with File Gateway, Volume Gateway, and Tape Gateway (**not S3**)
- 