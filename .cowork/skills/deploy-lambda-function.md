---
name: deploy-lambda-function
description: Deploy Lambda function with Terraform and validate deployment
trigger: "Deploy Lambda function to AWS"
---

# Deploy Lambda Function

## Steps

1. **Validate Terraform Configuration**
   ```bash
   terraform validate
   ```

2. **Plan Deployment**
   ```bash
   terraform plan -out=tfplan
   ```

3. **Apply Terraform Changes**
   ```bash
   terraform apply tfplan
   ```

4. **Wait for Lambda Deployment**
   ```bash
   aws lambda wait function-active --function-name $LAMBDA_NAME
   ```

5. **Run Smoke Tests**
   ```bash
   npm run test:smoke
   ```

6. **Post Deployment Status to Teams**
   - Send notification to #gestao-vulns-dev
   - Include Lambda ARN, version, and test results

## Success Criteria
- Terraform apply completes without errors
- Lambda function is active in AWS
- Smoke tests pass
- Teams notification sent
