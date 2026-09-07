# Prompt para Continuação - SSCV Development

**Data**: 2026-09-08  
**Próxima Fase**: ÉPICO 1 - Foundation Layer Development  
**Para usar**: Cole este prompt no Claude Code da empresa

---

## 🎯 Contexto

Projeto: **Gestão Inteligente de Vulnerabilidades (SSCV)**  
Repository: https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades.git

**Status Atual** (2026-09-07):
- ✅ GitHub repo inicializado com main + develop
- ✅ 10 skills criados (.cowork + .opencode)
- ✅ 3 workflows CI/CD deployados (ci.yaml, deploy.yaml, compliance.yaml)
- ✅ Documentação completa (README, AGENT_PROFILES, LAUNCH_CHECKLIST)
- ✅ ÉPICO 1 kickoff message pronto no TEAMS_KICKOFF_MESSAGE.md

**Pendente** (Manual no GitHub UI):
- [ ] Configurar GitHub Secrets (AWS, Tenable, Snyk, SonarQube, Teams Webhook)
- [ ] Habilitar Branch Protection Rules em main
- [ ] Postar mensagem kickoff em #gestao-vulns-dev (Teams)

---

## 📋 Prompt para Claude Code (Empresa)

```
Projeto: Gestão Inteligente de Vulnerabilidades (SSCV)

CONTEXTO:
- Repository: https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades.git
- Branch: develop (clone com git checkout develop após clonar)
- Linguagem: Português para markdown/docs em projeto
- Framework: Claude Code + GitHub Actions CI/CD + AWS Lambda

STATUS ATUAL (2026-09-07):
✅ PASSOS 2-7 COMPLETOS:
  - GitHub repo com estrutura de projeto
  - 10 skills (.cowork/5 + .opencode/5)
  - 3 workflows CI/CD (ci, deploy, compliance)
  - Documentação: README, AGENT_PROFILES, LAUNCH_CHECKLIST
  - TEAMS_KICKOFF_MESSAGE.md pronto

⏳ PENDENTE (Manual):
  - GitHub Secrets: AWS_ACCOUNT_ID, AWS_REGION, AWS_ROLE_TO_ASSUME, TENABLE_API_KEY, TENABLE_SECRET_KEY, SNYK_TOKEN, SONAR_TOKEN, TEAMS_WEBHOOK_DEPLOYMENT
  - Branch Protection: 2 reviews + status check (ci.yaml) em main
  - Teams Kickoff: Postar TEAMS_KICKOFF_MESSAGE.md em #gestao-vulns-dev

PRÓXIMAS TAREFAS (ÉPICO 1 - Weeks 0-2):

TASK 1: AWS Infrastructure Foundation [DevOps Lead - 5 dias]
- [ ] Terraform files para CloudTrail, Config, Security Hub
- [ ] Lambda execution roles e policies
- [ ] S3 buckets para deployment artifacts
- [ ] CloudWatch dashboards setup

TASK 2: Agent Framework Development [AI/ML Lead - 10 dias]
- [ ] Create vulnerability-analyzer-agent.py
- [ ] Create remediation-orchestrator-agent.py
- [ ] Create compliance-monitor-agent.py
- [ ] Create incident-response-agent.py
- [ ] Test agent prompts e outputs (use .opencode/skills/test-agent-prompt.md)

TASK 3: Tenable API Integration [Backend Lead - 8 dias]
- [ ] Create src/services/tenable-client.ts (API wrapper)
- [ ] Implement vulnerability data ingestion
- [ ] Setup CloudWatch metrics publishing
- [ ] Add retry logic + error handling

TASK 4: Dashboard MVP [Frontend Lead - 8 dias]
- [ ] Create React app structure (npx create-react-app)
- [ ] Implement D3.js vulnerability dashboard (use .opencode/skills/build-d3-dashboard.md)
- [ ] Real-time data integration
- [ ] Mobile responsive design

COMO PROCEDER:

1. Clone o repositório:
   git clone https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades.git
   cd Gest-o-inteligente-de-vulnerabilidades
   git checkout develop

2. Revise documentação:
   - README.md - Setup geral
   - docs/agents/AGENT_PROFILES.md - Agent details
   - .cowork/skills/ - DevOps/deployment reference
   - .opencode/skills/ - Frontend/testing reference

3. Configure GitHub Secrets (via GitHub UI):
   Settings → Secrets and variables → Actions
   - AWS_ACCOUNT_ID
   - AWS_REGION=us-east-1
   - AWS_ROLE_TO_ASSUME=arn:aws:iam::ACCOUNT:role/github-actions-role
   - TENABLE_API_KEY
   - TENABLE_SECRET_KEY
   - SNYK_TOKEN (de Snyk account)
   - SONAR_TOKEN (de SonarCloud)
   - TEAMS_WEBHOOK_DEPLOYMENT (webhook URL do Teams)

4. Configure Branch Protection (via GitHub UI):
   Settings → Branches → Add branch protection rule
   - Branch name pattern: main
   - ✓ Require a pull request before merging
   - ✓ Require approvals (2)
   - ✓ Require status checks to pass before merging
     - ci.yaml

5. Crie branches de work para cada TASK:
   git checkout -b feature/aws-infrastructure
   git checkout -b feature/agent-framework
   git checkout -b feature/tenable-integration
   git checkout -b feature/dashboard-mvp

6. Após iniciar trabalho em cada task:
   - Commit regularmente em feature branches
   - Crie PRs para develop (serão buildadas por ci.yaml)
   - Após aprovação, merge para develop
   - Quando task pronta, PR develop → main (com 2 reviews)

ESTRUTURA DE DIRETÓRIOS (criar conforme avança):
```
sscv/
├── terraform/              # Infrastructure as Code
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── modules/
│       ├── cloudtrail/
│       ├── config/
│       ├── security-hub/
│       └── lambda/
│
├── src/                    # Source code
│   ├── agents/            # AI agents
│   │   ├── vulnerability-analyzer.py
│   │   ├── remediation-orchestrator.py
│   │   ├── compliance-monitor.py
│   │   └── incident-response.py
│   │
│   ├── services/          # Backend services
│   │   ├── tenable-client.ts
│   │   ├── cloudwatch-metrics.ts
│   │   └── teams-notifier.ts
│   │
│   ├── frontend/          # React app
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   ├── Dashboard.tsx
│   │   │   │   ├── VulnerabilityChart.tsx
│   │   │   │   └── ...
│   │   │   └── App.tsx
│   │   └── package.json
│   │
│   └── tests/            # Test files
│       ├── unit/
│       ├── integration/
│       └── e2e/
│
├── .github/workflows/    # CI/CD (JÁ CRIADO)
├── .cowork/skills/       # DevOps skills (JÁ CRIADO)
├── .opencode/skills/     # Frontend skills (JÁ CRIADO)
├── terraform.tfvars      # Terraform variables (criar - não comitar secrets!)
├── .env.example          # Environment variables template
└── README.md             # (JÁ CRIADO)
```

COMMUNICATION:
- Daily standup: 09:00 AM UTC-3 em #gestao-vulns-dev (async preferred)
- Blockers: Postar em #gestao-vulns-blockers com @mention do owner
- SLA: 1h para P0, 4h para P1, next day para P2
- Task status: Update via GitHub Issues daily

PRÓXIMAS AÇÕES (primeira coisa amanhã):
1. Clonar repositório em computador da empresa
2. Ler README.md + AGENT_PROFILES.md
3. Confirmar task assignments no Teams (#gestao-vulns-dev)
4. Começar com TASK 1 (AWS infra) - Terraform files
5. Commit em feature branch, PR para develop

Dúvidas? Revise:
- LAUNCH_CHECKLIST.md - Configurações pendentes
- TEAMS_KICKOFF_MESSAGE.md - Task details + links
- .cowork/skills/ e .opencode/skills/ - Step-by-step guides
```

---

## ✅ Checklist antes de clonar amanhã

- [ ] Copie este arquivo (`DEVELOPMENT_PROMPT.md`)
- [ ] Acesse GitHub e configure Secrets (8 secrets listados acima)
- [ ] Acesse GitHub e configure Branch Protection (main branch)
- [ ] Tenha à mão: GitHub repo URL, Teams channels, AWS credentials
- [ ] Abra Claude Code na empresa
- [ ] Cole o prompt acima no Claude Code
- [ ] Siga as instruções do prompt

---

## 🔗 Links Importantes

| Recurso | URL |
|---------|-----|
| GitHub Repo | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades |
| Clone | `git clone https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades.git` |
| README | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/blob/main/README.md |
| Agent Profiles | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/blob/main/docs/agents/AGENT_PROFILES.md |
| Launch Checklist | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/blob/main/LAUNCH_CHECKLIST.md |
| Teams Kickoff | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/blob/main/TEAMS_KICKOFF_MESSAGE.md |
| .cowork skills | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/tree/main/.cowork/skills |
| .opencode skills | https://github.com/rcenerini/Gest-o-inteligente-de-vulnerabilidades/tree/main/.opencode/skills |

---

**Pronto para continuar amanhã! 🚀**

*Gerado em: 2026-09-07 23:30 UTC-3*
