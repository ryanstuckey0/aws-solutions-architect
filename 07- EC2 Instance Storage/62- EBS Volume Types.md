- EBS volumes come in 6 types
	- gp2 / gp3 (SSD): general purpose SSD with a good price to performance ratio
	- io1/io2 Blocker Express (SSD): highest performance SSD providing low latency and high throughput
	- st1 (HDD): low cost HDD volume for high throughput workloads
	- sc1 (HDD): lowest cost designed for infrequently accessed data

# SSD
- Only the SSD variants (gp2/gp3 + io1/io2) types can be used as boot volumes
- Gp2- cost effective, low latency, 1GiB - 16Gib size
	- volume size and IOPS are proportional
	- max IOPS is 16,0000
	- you get 3 IOPS per GB of storage, so max storage size is 16,000 / 3 = 5334 GB
- Gp3- IOPS independently set from volume

- Provisioned IOPS SSD (PIOPS SSD)
	- Offers sustained IOPS performance, > 16000 IOPS
	- good for database workloads
- io1 volume
	- storage ranges from 4 GiB - 16 TiB
	- Max PIOPS = 64000 for Nitro EC2 instance, else 32000
	- PIOPS can be changed independent of storage size
- io2 block express
	- Storage ranges from 4 GiB - 64 TiB
	- sub-millisecond latency
	- up to 256k IOPS, IOPS:GB ratio of 1k:1
- Supports EBS multi-attach

# HDD
- cannot be boot volume
- 125 GiB to 16 TiB
- st1- throughput optimized HDD
	- good for lots of data
	- up to 500 MiB/s and IOPS up to 500
- sc1- cold HDD
	- used for lowest possible cost and infrequent access
	- up to 250 MiB/s and IOPS up to 250

# Summary
- helpful info: https://docs.aws.amazon.com/ebs/latest/userguide/ebs-volume-types.html
- SSD volumes: [image](Pasted image 20240626195834.png)
- HDD volumes: [image](Pasted image 20240626195851.png)