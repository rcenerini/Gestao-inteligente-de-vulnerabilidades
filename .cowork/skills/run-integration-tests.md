---
name: run-integration-tests
description: Execute integration tests against AWS infrastructure
trigger: "Run integration tests"
---

# Run Integration Tests

## Steps

1. **Setup Test Environment**
   ```bash
   npm install
   export AWS_REGION=us-east-1
   export TEST_ENV=integration
   ```

2. **Start Test Infrastructure (if needed)**
   ```bash
   docker-compose -f docker-compose.test.yml up -d
   ```

3. **Run Integration Tests**
   ```bash
   npm run test:integration
   ```

4. **Collect Coverage Metrics**
   ```bash
   npm run test:coverage
   ```

5. **Publish Results to CloudWatch**
   - Push test metrics to CloudWatch Metrics
   - Include pass/fail rate, coverage %, execution time

6. **Generate Test Report**
   ```bash
   npm run test:report
   ```

## Success Criteria
- All integration tests pass
- Code coverage ≥ 80%
- Metrics published to CloudWatch
- Report generated and uploaded

## Teardown
```bash
docker-compose -f docker-compose.test.yml down
```
