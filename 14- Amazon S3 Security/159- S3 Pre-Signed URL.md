# 159- S3 Pre-Signed URL
- Can generate pre-signed URLs in S3 console, AWS CLI, or ADK
- Expires in 1 min to 12 hours to 168 hours
- A pre-signed URL allows the recipient to inherit the permissions of the user that generated the URL
- Use case- could give file access to an object in bucket for somebody outside of AWS (that normally wouldn't have permissions), upload a single file,
- All can be done w/o making your bucket fully public