# AWS Examples

Examples are illustrative. Confirm the AWS SDK, service, region, and project conventions before adapting them.

## Use the SDK Credential Chain (boto3)

```python
import boto3

session = boto3.Session(region_name="us-west-2")
s3 = session.client("s3")
```

The SDK can use configured profiles, environment configuration, or an attached role. Do not put access keys in this code.

## Inspect the Active AWS Identity

```powershell
aws sts get-caller-identity
```

Check the account and identity before running commands that change resources.

## Preview Infrastructure Changes

```powershell
aws cloudformation deploy `
  --template-file template.yaml `
  --stack-name example-stack `
  --no-execute-changeset
```

Review the proposed change set before executing it. Exact options and behavior may vary by AWS CLI version and deployment workflow.

## Scope an IAM Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:GetObject"],
      "Resource": "arn:aws:s3:::example-bucket/reports/*"
    }
  ]
}
```

Replace the example resource with the precise required ARN. Validate the policy against the full workflow and organizational controls before use.