# Creating an EFS
- Can choose name, VPC
	- Type- regional (multi-AZ), or one zone
	- Auto backups- for a price
	- Lifecycle management- comes set with default of 30 days for IA and 90 days for archive, and none for transition into standard
	- Encryption- on or off (use KMS)
	- Performance
		- Throughput mode
			- Choose enhanced to choose elastic or provisioned/fixed
				- Provisioned throughput shows you the price upfront
			- Choose bursting for it to scale with size
		- Performance mode
			- General purpose is available with enhanced throughput
			- Max I/O is available with bursting throughput
	- Recommended setting is elastic throughput with general purpose performance
- Network access
	- Choose VPC
	- Can choose mount targets (choose AZ depending on type of EFS)
		- AZ, subnet, and IP are automatic
		- Need to create security group or use default
			- Recommendation is to create one
- Can also configure custom file system settings
- Starts out very small (6KiB)

# Mounting EFS to EC2 Instances
- Create instances in each AZ that EFS is available in
- Attach FileSystem on EC2 config when creating- need to select a subnet first (subnet is in a specific AZ)
- Can select mount point also
- Will create and attach necessary security groups
	- Will also setup necessary inbound/outbound rules
- Will also run required user data scripts on boot to attach EFS to EC2 instance
- In EFS console, check network tab and look at security groups- should see groups auto-created by EC2 creation process

# Deleting EFS
- Delete EFS by entering its ID
- Also have to delete security groups auto created by attaching to EC2