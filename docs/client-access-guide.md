# Buyer AWS Access Guide

## Summary

To start the CloudWatch monitoring setup, I need **CLI/API access** first.

**AWS Console access** is also needed for visual dashboard, alarm, SNS, logs, and billing checks.

Root access is not needed. AdministratorAccess is not needed.

## Recommended Choice

For most non-technical buyers, use **Option 1: Temporary IAM user with Console + API access**.

For technical teams, use **Option 2: Temporary IAM role with External ID** or **Option 3: IAM Identity Center**.

## Access Options

| Option | Best for | Buyer shares |
| --- | --- | --- |
| [Option 1 - Temporary IAM user with Console + API](access-option-1-temporary-iam-user-console-api.md) | Easiest all-in-one setup | Console URL, username, temporary password, access key, secret key, region |
| [Option 2 - Temporary IAM role with External ID](access-option-2-temporary-iam-role.md) | Best for technical/security teams | Role ARN, External ID, region; no access key |
| [Option 3 - IAM Identity Center access](access-option-3-iam-identity-center.md) | Companies already using AWS SSO | Start URL, assigned user, account, permission set, region; no access key |
| [Option 4 - API / CLI access key only](access-option-4-api-cli-access-key.md) | API-only fallback | Access key, secret key, region |

## Policy File

Use this policy file:

- [`../iam-policy.json`](../iam-policy.json)

The same policy can be attached to a temporary IAM user, IAM role, or IAM Identity Center permission set.

Each option page lists exactly what to send after setup.

## After Delivery

After the project is delivered, remove the temporary access:

- Delete or deactivate the temporary IAM user.
- Delete the access key if one was created.
- Remove the role trust relationship.
- Remove the IAM Identity Center assignment.

## Official AWS References

- AWS IAM user creation: https://docs.aws.amazon.com/console/iam/add-users
- AWS customer managed policy creation: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html
- AWS access keys: https://docs.aws.amazon.com/cli/latest/reference/iam/create-access-key.html
- AWS third-party role access and External ID: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html
- AWS IAM Identity Center account assignments: https://docs.aws.amazon.com/singlesignon/latest/userguide/assignusers.html
