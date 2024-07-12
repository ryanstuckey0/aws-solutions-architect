# 133- S3 Versioning
- Files can be versioned- must be enabled at bucket level
- Will create a new version of file each time it is reuploaded at the same key
- Best practice is to version buckets- can easily restore deleted files or restore previous version
- note
	- Any file not versioned prior will have version null
	- Disabling versioning does not delete old versions 