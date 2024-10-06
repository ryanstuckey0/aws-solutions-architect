# 186- SQS FIFO Queue
- Enables first in first out polling of messages
- Used to guaranteed ordering
- Limited throughput- 300 message/s w/o batching, or 3000 messages/s w/ batching
- Also has exactly-once capability (removes duplicates)
- Messages are processed by consumer in the order they were produced
- **Queue name has to end with `.fifo`**
- Can enable or disable content-based de-duplication to remove duplicate messages if produced within same 5 minute window
- When sending messages, specify message body, message group ID, and message deduplication ID