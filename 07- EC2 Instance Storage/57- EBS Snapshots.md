- Backup at any point in time of EBS volume
- No need to detach from EC2 instance, but is recommended
- Can move snapshots across AZ
- EBS snapshot archive
	- Can move snapshots to archive tier that is ~75% cheaper
	- Takes between 24-72 hours to restore archive
- Recycle bin
	- Can be used to recover snapshots from accidental deletion
	- Snapshots can be retained for 1 day up to 1 year
- Fast snapshot restore (FSR)
	- Forces a full initialization of snapshot
	- Allows almost no latency when using for first time
	- Very expensive
	- Helpful for big snapshots and useful when you need to initialize an EBS volume very quickly
	- 