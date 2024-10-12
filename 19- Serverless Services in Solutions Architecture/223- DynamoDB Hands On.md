# 223- DynamoDB Hands On
- Right away, we can create a table; no need to create database
- Need to specify partition key and optional sort key right away
- Can choose default or custom settings
- Choose RW capacity settings- on demand or provisioned
	- On-demand will be 2-3 times more expensive than provisioend
- For provisioned, need to choose RCU and WCU\
	- With autoscaling, set min/max units, and target usage (%)
	- Also has a usage calculator that can be used
- Can also create secondary indices
- Can see estimated cost at end based on capacity units provisioned

## Creating and Viewing Items
- Creating the first item- need to specify all atributes to add 
- Each newly created item can have different attributes
- 