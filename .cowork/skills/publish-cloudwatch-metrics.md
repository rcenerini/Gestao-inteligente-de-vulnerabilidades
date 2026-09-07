---
name: publish-cloudwatch-metrics
description: Publish application and deployment metrics to AWS CloudWatch
trigger: "Publish metrics to CloudWatch"
---

# Publish CloudWatch Metrics

## Steps

1. **Authenticate with AWS**
   ```bash
   aws sts get-caller-identity
   ```

2. **Collect Application Metrics**
   - Lambda invocations and errors
   - API latency and throughput
   - Database query performance
   - Memory and CPU utilization

3. **Publish Metrics to CloudWatch**
   ```bash
   aws cloudwatch put-metric-data \
     --namespace "SSCV/Application" \
     --metric-name "SuccessfulInvocations" \
     --value $INVOCATIONS \
     --unit Count
   ```

4. **Create Custom Dashboards**
   - Vulnerability detection rate
   - Remediation success rate
   - Mean time to resolution (MTTR)
   - Compliance coverage %

5. **Setup CloudWatch Alarms**
   - High error rate (> 5%)
   - Lambda timeout (> 30s)
   - Database connection pool exhaustion
   - Insufficient capacity

6. **Enable Log Insights Queries**
   - Security events
   - API errors
   - Performance degradation

## Success Criteria
- Metrics visible in CloudWatch dashboard
- Alarms configured and active
- Historical data retention: 30 days
