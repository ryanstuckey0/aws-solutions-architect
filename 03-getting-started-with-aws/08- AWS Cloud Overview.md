- Launched internally in 2002
- AWS is considered one of the leaders in cloud provides
- 47% market share in 2019 (Microsoft 2nd with 22%)

## Use Cases
- Build scalable applications
- Use to store data, host website, analyze data, gaming server, and so on

## Infrastructure
- Can view the infrastructure at [infrastructure.aws](https://infrastructure.aws)

### Regions
- Each region is a cluster of data centers
- Most AWS services are region scoped
- How do you choose an AWS region?
	- Compliance- gov't might require data to be located in one region
	- Proximity- deploy based on where customers are located
	- Available services- not all regions have all services, depends on what services you need to use
	- Pricing- varies from region to region 

#### Availability Zones
- Each region can have a min of 3 and a max of 6 availability zones
- Each AZ is one or more discrete datacenters with their own power, networking, etc.
- Each DC is separated from others, so all AZ in a region will not all be affected
- All DC are connected physical low latency, high speed connection
- Has availability across 90+ cities and 40+ countries

Some services are global, but most are region scoped