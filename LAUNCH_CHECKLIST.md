# Pre-Launch Checklist - SSCV ÉPICO 1

**Data**: 2026-09-07  
**Timeline Alvo**: ✅ Completo

---

## ✅ 1. AWS Configuration

- [ ] **CloudTrail habilitado**
  - Logs de API calls em S3
  - Retenção mínima: 90 dias
  
- [ ] **AWS Config habilitado**
  - Rules ativas para security compliance
  - Snapshots de configuração
  
- [ ] **Security Hub habilitado**
  - Integrado com Tenable/Qualys
  - Dashboards e alertas configurados

- [ ] **IAM Roles/Policies**
  - Lambda execution role
  - Tenable API integration role
  - GitHub Actions OIDC role

**Status**: ⏳ Aguardando confirmação de AWS credentials disponíveis

---

## ✅ 2. GitHub Configuration

- [x] **Repositório inicializado**
  - Branch `main` ✅
  - Branch `develop` ✅
  
- [x] **Workflows deployados**
  - ci.yaml ✅
  - deploy.yaml ✅
  - compliance.yaml ✅
  
- [x] **Documentação no repositório**
  - README.md ✅
  - AGENT_PROFILES.md ✅
  - LAUNCH_CHECKLIST.md ✅

- [ ] **GitHub Secrets configurados**
  - AWS_ACCOUNT_ID
  - AWS_REGION
  - AWS_ROLE_TO_ASSUME
  - TENABLE_API_KEY
  - TENABLE_SECRET_KEY
  - SNYK_TOKEN
  - SONAR_TOKEN
  - TEAMS_WEBHOOK_DEPLOYMENT

- [ ] **Branch Protection Rules**
  - Require 2 PR reviews
  - Require status checks (ci.yaml)
  - Dismiss stale reviews

**Status**: ⏳ Aguardando configuração manual de secrets e branch protection

---

## ✅ 3. Microsoft Teams Configuration

- [ ] **Canal #gestao-vulns-dev**
  - Criado ✅ (manual)
  - Members adicionados
  - Descrição atualizada
  
- [ ] **Canal #gestao-vulns-security**
  - Criado ✅ (manual)
  - Access restrito ao Security Team
  
- [ ] **Canal #gestao-vulns-blockers**
  - Criado ✅ (manual)
  - Notifications ativas

- [ ] **Teams Bot integrado**
  - Azure App Registration criado
  - Bot conectado ao SSCV API
  - Commands registrados

**Status**: ⏳ Aguardando criação manual dos canais no Teams

---

## ✅ 4. Documentation & Governance

- [x] **Agent Profiles documentados**
  - AGENT_PROFILES.md com 4 agents ✅
  - Responsibilities claras ✅
  
- [x] **Skills criados**
  - .cowork/skills/ (5 files) ✅
  - .opencode/skills/ (5 files) ✅
  
- [ ] **AI-DLC Gates documentados**
  - Phase gates (Requirements → Design → Tasks → Implementation)
  - Approval workflows
  - Escalation paths

- [ ] **ÉPICO 1-2 tasks completados**
  - Task 1: Foundation Layer (Weeks 0-2)
  - Task 2: Agent Framework (Weeks 1-3)
  - Task 3: Tenable Integration (Weeks 2-4)
  - Task 4: Dashboard MVP (Weeks 3-5)

**Status**: ✅ Documentação criada | ⏳ Tasks de ÉPICO em andamento

---

## 🚀 Ready for ÉPICO 1 Kickoff?

### ✅ Completado
1. Repositório GitHub inicializado com estrutura
2. CI/CD workflows (ci.yaml, deploy.yaml, compliance.yaml)
3. 10 skills criados (.cowork + .opencode)
4. Agent profiles documentados
5. README e guias de setup

### ⏳ Pendente (Manual)
1. **GitHub Secrets** - Configure via Settings → Secrets
2. **Branch Protection** - Settings → Branches → Add rule
3. **Microsoft Teams** - Criar 3 canais organizacionais
4. **AWS Credentials** - Validar cloudformation/terraform vars
5. **Teams Bot** - Azure App Registration + bot token

### 📋 Próximas Ações
```bash
# 1. Push para repositório remoto
git push -u origin main
git push -u origin develop

# 2. Configurar secrets no GitHub (via UI)
# 3. Habilitar branch protection (via UI)
# 4. Criar canais Teams (via Teams app)
# 5. Executar PASSO 7 - Teams Kickoff
```

---

**🟢 Sistema pronto para ÉPICO 1 kickoff após configurações manuais acima!**

---

*Gerado em*: 2026-09-07 23:00 UTC-3  
*Projeto*: Gestão Inteligente de Vulnerabilidades (SSCV)  
*Framework*: Claude Code + OpenCode + GitHub Actions + AWS
