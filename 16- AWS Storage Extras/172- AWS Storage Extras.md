# 172- AWS Storage Extras
- Two use cases
	- Collect and process data at the edge
	- Migrate data in and out of AWS
- Three types

| Type          | Data migration | Edge computing |
| ------------- | -------------- | -------------- |
| Snowcone      | X              | X              |
| Snowball Edge | X              | X              |
| Snowmobile    | X              |                |

## Data Migration w/ SNOW
- Takes a long time to transfer a lot of data over network- 12 days over a 1Gbps connection for 100 TB
- Also have some limitations- like connectivity, bandwidth limit, network cost, shared bandwidth
- AWS Snow offers offline data migrations
	- Use if it takes >1 week to transfer data

## How does data migration with Snow work?
- Request AWS Snowball device
- Load data onto device
- Ship back to AWS
- AWS plugs device into internal network to load data


## Snow Types
### Snowball Edge
- Move TBs or PBs of data in/out of AWS network
- Pay per amount of data used
- Uses block storage or S3 compatible object storage
- Two classes
	- Storage optimized- 80 TB HDD or 210 TB NVMe
	- Compute optimized- 42 TB HDD or 28 TB NVMe
- Use cases: large data to cloud migrations, DC decommission, disaster recovery

### Snowcone
- Smaller, portable, rugged, withstand harsh environments
- Light- 2.1 kg
- Two classes
	- Snowcone- 8TB of HDD 
	- Snowcone SSD- 14TB SSD
- User provides battery/cables
- Can send back to AWS or connect to AWS Datasync

### Snowmobile
- This is an actual truck that transfers data
- Transfer exabytes of data (1 EB = 1000 PB = 1,000,000 TB)
- Each snowmobile has 100 PB of capacity
- high security, temperature controlled, GPS, 24/7 video surveillance
- Better than snowball if transferring more than 10PB


## Using a Snow family device
1. Request device from AWS
2. Install snowball client / AWS OpsHub on your servers
3. Connect snowball to servers and copy files via client
4. Ship back to AWS (goes straight to datacenter)
5. Loaded into S3
6. Snowball is completely wiped

## Edge computing w/ Snow
- Process data while it is being created at edge locations
- An edge location will be anywhere that doesn't have Internet or is far away from the cloud
	- Won't have Internet connectivity, or very limited access
- Can use a Snowball Edge or Snowcone device to do edge computing
- Could be
	- Preprocess data (reduce footprint)
	- Machine learning
	- Transcode media streams

### Types
- Snowcone or Snowcone SSD
	- 2 CPU, 4GB RAM
	- USB-C power cord or batter
- Snowball Edge, compute optimized
	- 104 vCPU, 416 GB RAM
	- Optional GPU (could be used for ML or video transcoding)
	- 28TB NVMe ot 42TB HDD
	- Can cluster up to 16 nodes
- Snowball Edge, storage optimized
	- Up to 40 vCPU, 80 GB RAM
	- 80 TB Storage
- Can run EC2 instances or AWS Lambda functions
	- Uses AWS IoT Greengrass
- Can deploy for long term- 1 or 3 years w/ discounted pricing

## OpsHub
- Historically needed to use CLI to work with Snow devices
- They releases OpsHub, which is something you can install on your local computer to work with Snow devices
- Can do several tasks from here-
	- Configure single/clustered devices
	- Transfer files
	- Monitor device metrics
		- Launch compatible AWS services