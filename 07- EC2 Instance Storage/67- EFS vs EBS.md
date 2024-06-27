# EBS
- EBS volumes- only one instance (except io1/ios2 muli-attach)
- Locked to a single AZ
- gp2- IO is proportional to size
- gp3 & ios1- IO can be statically set
- Migrate across AZ w/ snapshot
- root volume gets terminated if EC2 instance is terminated by default

# EFS
- can attach to 100s of instance across AZ
- only for Linux
- High cost than EBS- but can use tiers to save money
- 

