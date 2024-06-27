- Elastic file system - EFS
- Managed network file system (NFS)
- can be mounted on many EC2 instances, and across multiple instances
- Highly available, scalable, and expensive (3x EBS gp2 cost)
- Surround EFS with security group and then let EC2 instances connect to it with matching security group/permission
- Uses NFSv4.1
- **Only compatible with Linux based AMI** (not Windows)
- Encryption at rest using KMS
- POSIX file system,
- File system scales scales automatically
- Pay per GB

# Performance and Storage Classes
- Scale (changes throughout lifetime)
	- can have 1000s of NFS clients
	- Up to 10GB/s throughput
	- Can grow up to Petabytes of data
- Performance mode (set at creation)
	- **General purpose**- low latency
	- **Max I/O**- higher latency, but high throughput
- Throughput mode
	- **Bursting** - scales with size of EFS; 1 TB = 50 MiB/s + bursts of up to 100MiB/s
	- **Provisioned**- set static throughput; independent of storage size
	- **Elastic**- scale up or down automatically based on workload
		- Max of 3GiB/s for reading and 1GiB/s for writing
## Storage Classes
- Storage tiers
	- lifecycle management feature
	- move files to different tiers based on number of days
- Storage tier types
	- **Standard**- for frequently accessed files
	- **Infrequent access (EFS-IA)**- cost to retrieve files, but lower storage cost
	- **Archive**- very low cost (50% cheaper), only access couple times per year
- Use lifecycle policies to move between Storage tiers
## Availability and durability
- **Standard**- Multi-AZ, good for prod workloads
- One zone: one AZ, good for dev/UAT envs, still has backups and and compatible with EFS-IA