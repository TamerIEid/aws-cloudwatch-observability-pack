# Option 4 - API / CLI Access Key Only

## Summary

Use this option when you want me to start with discovery, Terraform planning, validation, and report generation without AWS Console login.

This can be enough for many setups. Console access can be added later if visual dashboard/alarm review is needed.

## Step 1 - Create Temporary IAM User

Open the AWS Console and go to:

```text
IAM -> Users -> Create user
```

Username:

```text
cloudwatch-monitoring-api-temp
```

Do not enable console access for this option.

## Step 2 - Create The Policy

Go to:

```text
IAM -> Policies -> Create policy -> JSON
```

Open:

```text
public/iam-policy.json
```

Copy the JSON into the AWS policy JSON editor.

Policy name:

```text
CloudWatchMonitoringSetupLimitedPolicy
```

![Paste policy JSON](../media/access-guide/iam-policy-json.svg)

## Step 3 - Attach The Policy

Attach:

```text
CloudWatchMonitoringSetupLimitedPolicy
```

to:

```text
cloudwatch-monitoring-api-temp
```

## Step 4 - Create Access Key

Open the IAM user:

```text
Security credentials -> Access keys -> Create access key
```

Choose:

```text
Command Line Interface (CLI)
```

![Create access key](../media/access-guide/access-key.svg)

## Step 5 - Send These Details

```text
AWS_ACCESS_KEY_ID:
AWS_SECRET_ACCESS_KEY:
AWS_REGION:
Billing region: us-east-1
Notification email:
Billing threshold:
Approved resources or services:
```

## Step 6 - Optional Console Access Later

If screenshots or visual checks are needed later, add console access or create a separate console user.

## Step 7 - Remove Access After Delivery

After delivery:

- Delete the access key.
- Delete the temporary IAM user.
