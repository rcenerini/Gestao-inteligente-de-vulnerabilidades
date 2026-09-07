---
name: escalate-blocker
description: Escalate blockers and critical issues to Microsoft Teams
trigger: "Escalate blocker to team"
---

# Escalate Blocker

## Steps

1. **Identify Blocker**
   - Type: Infrastructure, Security, Dependency, External API
   - Severity: Critical (P0), High (P1), Medium (P2)
   - Duration: How long it's been blocking

2. **Notify #gestao-vulns-blockers Channel**
   ```
   🚨 BLOCKER ESCALATION
   
   **Type**: [Infrastructure/Security/Dependency/External API]
   **Severity**: [P0/P1/P2]
   **Issue**: [Description]
   **Impact**: [Teams/Services affected]
   **Duration**: [Time blocked]
   **Owner**: [Assigned engineer]
   **SLA**: 1h response for P0, 4h for P1
   
   Thread: [Link to PR/Issue]
   ```

3. **Notify Team Lead**
   - Direct mention in Teams: @Team Lead
   - Include blocker details
   - Request action/decision

4. **Create Issue Tracking**
   - Create GitHub issue with blocker label
   - Reference Teams thread
   - Link to related PRs/tickets

5. **Monitor Resolution**
   - Track status updates in thread
   - Update every 30 min for P0
   - Every 2h for P1/P2

6. **Close Blocker**
   - Confirm resolution with team
   - Post final status in thread
   - Document workaround/solution

## Success Criteria
- Team notified within 5 min
- Assigned to owner within 30 min
- Resolved per SLA targets
