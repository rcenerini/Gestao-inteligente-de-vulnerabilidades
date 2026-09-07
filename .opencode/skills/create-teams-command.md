---
name: create-teams-command
description: Create Microsoft Teams bot command for vulnerability queries
trigger: "Create Teams vulnerability command"
---

# Create Microsoft Teams Command

## Steps

1. **Register Teams Bot Application**
   - Create Azure App Registration
   - Configure OAuth2 permissions
   - Generate bot token

2. **Setup Bot Framework SDK**
   ```bash
   npm install botbuilder botbuilder-dialogs
   ```

3. **Create Command Handlers**
   - `/vuln-status` - Query vulnerability status
   - `/escalate` - Escalate critical issues
   - `/remediation-plan` - Get remediation steps
   - `/compliance-check` - Check compliance status
   - `/incident-report` - Generate incident report

4. **Implement Interactive Cards**
   - Adaptive Cards for vulnerability details
   - Action buttons for approval/rejection
   - Rich formatting with markdown

5. **Configure Message Routing**
   - Channel messages: #gestao-vulns-dev
   - Direct messages: For escalations
   - Threaded replies: For discussions

6. **Add Authentication & Authorization**
   - User role verification
   - Rate limiting
   - Audit logging

## Success Criteria
- All 5 commands working
- Adaptive cards displaying correctly
- User permissions enforced
- Commands discoverable in Teams UI
- Response time < 3 seconds
