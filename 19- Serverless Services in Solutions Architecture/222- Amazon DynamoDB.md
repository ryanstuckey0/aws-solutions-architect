# 222- Amazon DynamoDB
- Fully managed, highly available, replicates across multiple DB
- NoSQL database, w/ transaction support
- Since it's distributed, can scale to massive workloads- millions of requests / second, trillions of rows, 100s TB of storage
- Very fast- single-digist ms
- Full integration w/ IAM 
- Low cost, auto scaling
- No maintenance or patching, always available
- No need to provision- just create tables and you're ready to go
- Two table classes- Standard and infrequent access (IA)

## Basics
- Fully made of tables, but no need to create DB
- Each table has a primary key
- Each table can have an infinite number of items (i.e., rows)
- Each item has attributes, and can add more over time
- Max item size- 400 KB
- Data types
	- Scalar- String, Number, Binary, Boolean, Null
	- DocumentTypes- List, Map
	- Set Types- String Set, Number Set, Binary Set
- **Great to use when you have rapidly evolving schemas**

- Has primary key, optional sort key, and then attributes

## Read/Write Capacity Modes
- With these you can control your table's capacity
- Provisioned mode (default)
	- Can specify number of reads/writes per second
	- Need to plan capacity beforehand
	- Pay for provisioned read capacity units (RCU) and write capacity unites (WCU)
	- Can also add auto-scaling for RCU and WCU
	- Best if you know the required demand/load ahead of time
- On-Demand Mode
	- RW capacity scale automatically w/ workload
	- Pay exactly for what you use- which is every single read, and every single write
	- So much more expensive
	- Great for unpredictable workloads, steep sudden spikes
		- Provisioned mode is not good because it will not scale quickly enough with spikes
	- 