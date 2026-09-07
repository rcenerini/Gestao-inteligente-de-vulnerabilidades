---
name: generate-e2e-test
description: Generate end-to-end tests with Playwright
trigger: "Generate E2E tests"
---

# Generate E2E Tests

## Steps

1. **Setup Playwright Test Framework**
   ```bash
   npm install -D @playwright/test
   npx playwright install
   ```

2. **Create Test Structure**
   - tests/e2e/auth.spec.ts
   - tests/e2e/dashboard.spec.ts
   - tests/e2e/vulnerability-flow.spec.ts
   - tests/e2e/teams-integration.spec.ts

3. **Implement Auth Flow Tests**
   - Login with valid credentials
   - Login with invalid credentials
   - Session persistence
   - Logout functionality

4. **Implement Dashboard Tests**
   - Page load and chart rendering
   - Filter functionality
   - Real-time data updates
   - Export functionality

5. **Implement Vulnerability Flow Tests**
   - Create vulnerability record
   - Update vulnerability status
   - Escalate to Teams
   - Generate remediation plan

6. **Add Teams Integration Tests**
   - Bot command execution
   - Adaptive card rendering
   - Message threading
   - Approval workflow

## Success Criteria
- All test scenarios pass
- Code coverage ≥ 85%
- Tests run in CI/CD pipeline
- Parallel execution working
- Screenshots captured on failure
