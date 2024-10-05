# 180- Datasync
- Moves data to and from various locations
	- On-prem/other cloud <--> AWS (requires agent on client)
	- Move data between AWS services 
- Can sync data to - S3 (including Glacier), EFS, FSx
- Replication tasks are not asynchronous, must set schedule
- Can keep file metadata and permissions (NFS POSIX, SMB)
- One agent can handle up to 10Gbps, but can set limit
- If user wants Datasync but does not have capacity for it, they can get a physical snow cone device as it has Datasync pre-installed on it
- Can also use to sync between AWS services