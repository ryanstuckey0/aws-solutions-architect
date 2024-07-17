# 163- S3 Object Lambda
- Goal is to modify object just before it is retrieved from bucket
- What if we need slightly different versions of each object? instead of duplicating bucket with slightly varied versions, we can use object lambda instead
- used alongside an S3 Access Point and an S3 Object Lambda access point
- Some lambda would be called when the S3 Access Point access the object
- By doing this, all clients can access the same object, with each object retrieval customized via a lambda function
![450](attachments/Pasted%20image%2020240716224832.png)

- Use cases- redact PII data, convert data between file formats, transform/resize/watermark images