# 190- SNS Hands On
- Can choose either standard or FIFO when creating topic
	- Like SQS, FIFO must also end with `.fifo`
- Need to specify access policy based on who is writing to SNS topic
- Then need to create subcription; supported protocols- KDF, SQS, Lambda, Email, HTTP/S, SMS
- Can also add a filter
- Subscribers need to validate subcription
	- In the case of email, the target will receive a confirmation email to their address
	- 
