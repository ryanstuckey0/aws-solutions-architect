# 184- SQS Message Visibility Timeout
- When a message is pulled by a consumer, it is invisible to other consumers for the length of the visibility timeout (default 30 s)
- During the visibility timeout, other consumers will not receive this message from polling
- If the message is still not deleted and the visibility timeout has finished, then consumers can receive the message when they poll
- Messages can be potentially processed twice if they are not completed within the visibility window
- If a consumer knows they will need more time to process a message, they can call the ChangeMessageVisibility API to get more time
- Setting the timeout too high will cause a large delay in reprocessing if the consumer crashes
- Setting the timeout too short could cause a large number of messages to be repeated if consumers don't have enough time to process before the timeout ends
- Visibility timeout can be set to anything between 0 seconds and 12 hours