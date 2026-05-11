# Sample Alarm Baseline

These are example alarm ideas. Actual thresholds should be reviewed against workload type, normal traffic, business priority, and AWS service limits.

| Area | Example Alarm | Example Threshold |
| --- | --- | --- |
| EC2 | `example-prod-web-01--cpu-high` | Average CPU greater than 95% for a sustained period |
| EC2 | `example-prod-web-01--memory-high` | Memory used greater than 95% for a sustained period |
| EC2 | `example-prod-web-01--root-disk-high` | Root disk used greater than 90% |
| EC2 | `example-prod-web-01--status-check-failed` | StatusCheckFailed greater than or equal to 1 |
| ALB | `example-prod-alb--target-5xx-high` | Sustained target 5xx errors |
| ALB | `example-prod-alb--unhealthy-hosts` | Unhealthy host count greater than 0 |
| RDS/Aurora | `example-prod-db--cpu-high` | Average CPU greater than 95% for a sustained period |
| RDS/Aurora | `example-prod-db--connections-high` | Client-approved connection threshold |
| RDS/Aurora | `example-prod-db--read-latency-high` | Sustained read latency above agreed threshold |
| Billing | `example-prod-billing--estimated-charges-high` | Estimated charges greater than approved monthly amount |

## Naming Pattern

Recommended alarm names:

`<project>-<environment>-<resource-name>--<condition>`

Example:

`example-prod-web-01--cpu-high`
