---
name: aws
description: Use for AWS architecture, SDKs, IAM, deployment, infrastructure as code, and troubleshooting.
---

# AWS Skill Reference

## Scope

Use this context for AWS architecture, SDK usage, IAM, deployment, infrastructure as code, and troubleshooting. Confirm the services and deployment model relevant to the task instead of assuming them.

## Security and Operations

- Apply least privilege to IAM identities and resource policies. Avoid wildcard permissions unless the exact need and risk are explained.
- Prefer IAM roles and short-lived credentials, such as the AWS SDK default credential provider chain, over long-lived access keys.
- Never request, expose, log, or commit AWS credentials, session tokens, private keys, or secret values.
- Treat region, account, environment, and resource ownership as explicit inputs. Avoid hard-coding them when configuration is appropriate.
- Consider encryption, network exposure, logging, retention, backup, and recovery for resources that handle sensitive or important data.
- Check cost and quota implications before recommending or creating resource-intensive services.
- Prefer repeatable infrastructure as code for managed environments. Follow the project's existing tool, such as AWS CDK, CloudFormation, or Terraform.

## Change Safety

- Distinguish read-only inspection from actions that create, modify, expose, or delete resources.
- Explain impact and request confirmation before destructive, externally visible, or potentially costly actions.
- Use plan, diff, or preview features before applying infrastructure changes when available.
- Verify resource state and relevant logs after deployment; do not infer success merely from a successful command exit.

## Assumptions

AWS service behavior and pricing change. Check current official AWS documentation for version-sensitive, security-sensitive, or cost-sensitive recommendations. State the assumed region and service when they affect the answer.