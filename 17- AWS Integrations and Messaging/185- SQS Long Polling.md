# 185- SQS Long Polling
 - When a consumer requests messages from a queue, it can wait for messages to arrive if there are none in the queue
	 - Reduces latency and # of API calls to SQS
 - This is called Long Polling
 - Can set the polling time between 1-20 seconds
 - Long Polling can be enabled at the queue level (enabled for all consumers), or use API call WaitTimeSeconds
 - 