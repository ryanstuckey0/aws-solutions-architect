# 156- MFA Delete Hands On
- Create a new bucket with versioning enabled
- In the properties tab, scroll down to the bucket versioning section and see that MFA delete is currently disabled
- However, we cannot enable this on the AWS console- we must use the CLI to enable it
- MFA must be setup in accounts before enabling this
- Setup CLI using access keys

```bash
aws configure
aws s3api put-bucket-versioning --bucket ${bucket-name} --versioning-configuration Status=enabled,MFADelete=Enabled --mfa "${mfa_device_arn} ${mfa_code}" --profile ${profile}
```

- To test this, we can check bucket properties, or try deleting an object version
- To disabled MFA delete, use the same command but set MFADelete=Disabled

```bash
aws configure
aws s3api put-bucket-versioning --bucket ${bucket-name} --versioning-configuration Status=enabled,MFADelete=Enabled --mfa "${mfa_device_arn} ${mfa_code}" --profile ${profile}
```

