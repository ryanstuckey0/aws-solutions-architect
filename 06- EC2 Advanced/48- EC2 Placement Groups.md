- Control how EC2 instances are placed compared to one another
- Three strategies available
	- Cluster- group into low-latency group within 1 hardware rack
	- Spread- spreads instances in their own distinct rack (max 7 per group per AZ); critical applications
	- Partition- spreads instances across partitions within different racks of hardware within AZ; can run up to 100s of instances
- Cluster
	- Pros: Place all within same AZ, low latency + 10 Gbps network
	- Cons: If AZ fails, all instances fails
	- Use case: big data job, extreme low latency, high bandwidth
- Spread
	- Pros: Instances are each located on a different rack (max 1 per rack), 
	- Cons: Limited to 7 instances per AZ per placement group, higher latency
	- Use case: maximum availability, failures must be isolated from one another
- Partition
	- Instances: each partition has several instances in one rack, and several partitions across AZ, up to 7 per AZ
	- Pros: Instances are distributed among several hardware racks, so isolated from entire rack failure, 100s of EC2 instances per group, span multiple AZ; balance between performance and availability
	- Cons: 
	- Use case: big data applications, Kafka, distributed apps

A helpful StackOverflow article- ![[Pasted image 20240626210635.png]]

From this question on [StackOverflow](https://stackoverflow.com/questions/56447086/aws-ec2-placement-groups-partition-vs-spread)