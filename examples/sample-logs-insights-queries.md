# Sample CloudWatch Logs Insights Queries

These examples are generic and must be adapted to the real log format.

## Nginx 5xx Errors

```sql
fields @timestamp, @message
| filter @message like / 5\d\d /
| sort @timestamp desc
| limit 50
```

## PHP Errors

```sql
fields @timestamp, @message
| filter @message like /PHP Fatal error|PHP Warning|PHP Notice/
| sort @timestamp desc
| limit 50
```

## Application Exceptions

```sql
fields @timestamp, @message
| filter @message like /Exception|Traceback|ERROR|CRITICAL/
| sort @timestamp desc
| limit 100
```

## Slow Requests

```sql
fields @timestamp, @message
| filter @message like /request_time/
| sort @timestamp desc
| limit 100
```

