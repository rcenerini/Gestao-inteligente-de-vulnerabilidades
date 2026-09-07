---
name: validate-terraform-config
description: Validate Terraform configuration for syntax and best practices
trigger: "Validate Terraform configuration"
---

# Validate Terraform Configuration

## Steps

1. **Check Terraform Syntax**
   ```bash
   terraform fmt -recursive .
   terraform validate
   ```

2. **Run TFLint for Best Practices**
   ```bash
   tflint --init
   tflint
   ```

3. **Validate Security Settings**
   - Verify encryption is enabled (S3, RDS, EBS)
   - Check IAM policies follow least privilege
   - Validate security group rules

4. **Check AWS Cost Estimates**
   ```bash
   terraform plan -out=tfplan
   terraform show -json tfplan | jq '.resource_changes[] | select(.type=="aws_*")'
   ```

5. **Generate Terraform Documentation**
   ```bash
   terraform-docs markdown table . > docs/TERRAFORM.md
   ```

## Success Criteria
- No syntax errors
- All TFLint warnings addressed
- Security validation passed
- Documentation generated
