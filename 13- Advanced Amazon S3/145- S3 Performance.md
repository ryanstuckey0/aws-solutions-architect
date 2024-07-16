# 145- S3 Performance
- AWS S3 auto-scales to high request rates, latency 100-200ms
- Can get up to 3500 put/copy/post/delete operations per second, or 5500 get/head requests per second per prefix per bucket- very fast
- No limits to number of prefixes in bucket
- What's a prefix? Anything between bucket name and file
	- bucket/folder1/subfolder1/file -> /folder1/sub1
	- bucket/folder1/subfolder2/file -> /folder1/sub2
	- bucket/1/file -> /1/
	- bucket/2/file -> /2/
- So based on the above 4 prefixes, we can achieve 22,000 get/head requests per second 

## Optimizing Performance
- Recommended to use multi-part upload for files over 100 MB
	- Must use for files over 5 GB
- Parallelize file uploads- allows for multiple parts to be uploaded at same time
- S3 Transfer Acceleration
	- Increase transfer speed by first transferring to AWS edge location, which then forwards data to S3 bucket in final region
	  ![](attachments/Pasted%20image%2020240715180726.png)
	- Compatible with multi-part upload
	- Faster because some of the transfer goes through private AWS network

## S3 Byte-Range Fetches
- Parallelize get by requesting specific byte ranges
- Provides better resiliency in failure since we can only re-download the parts we need
- Can be used to speed up downloads
- Can also be used to only retrieve a partial amount of a file ![](attachments/Pasted%20image%2020240715180916.png)
