# Sample Terraform Plan Summary

This is an example plan summary using demonstration values.

## Example Plan Result

```text
Plan: 18 to add, 2 to change, 0 to destroy.
```

## Example Resources

| Resource Type | Count | Purpose |
| --- | ---: | --- |
| CloudWatch dashboard | 1 | Main monitoring view |
| CloudWatch metric alarms | 14 | Workload and billing alerting |
| SNS topic | 1 | Email notification routing |
| SNS subscription | 1 | Alert recipient confirmation |
| CloudWatch Logs retention updates | 2 | Apply approved retention period |

## Example Review Notes

- No resources are destroyed.
- Log retention updates change retention policy only.
- Billing alarm must be created in the supported billing metric region.
- SNS email delivery requires recipient confirmation.
- Production apply should happen only after written approval.
