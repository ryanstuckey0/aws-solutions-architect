# 181- Intro
- Applications can communicate using either:
	- synchronous- app to app communication
	- asynchronous- app to queue to app

## Synchronous Communication
- Services can get overwhelmed if there is a large spike in requests
- It is best to decouple the application when the # of requests is unpredictable/erratic 
	- SQS- queue model
	- SNS- pub/sub model
	- Kinesis- real time streaming