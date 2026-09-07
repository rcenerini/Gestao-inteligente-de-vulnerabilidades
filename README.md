# Gestão Inteligente de Vulnerabilidades (SSCV)

Sistema integrado de detecção, análise e remediação automática de vulnerabilidades com inteligência artificial.

## Estrutura do Projeto

```
sscv/
├── docs/agents/          # Documentação de agents AI
├── .cowork/skills/       # Skills para workflow colaborativo
├── .opencode/skills/     # Skills para OpenCode
├── .github/workflows/    # CI/CD workflows
└── README.md
```

## Configuração Inicial

### 1. GitHub Secrets (via Settings → Secrets and variables)
Configure os seguintes secrets no repositório:
- `AWS_ACCOUNT_ID`
- `AWS_REGION` (us-east-1)
- `AWS_ROLE_TO_ASSUME`
- `TENABLE_API_KEY`
- `TENABLE_SECRET_KEY`

### 2. Branch Protection
Settings → Branches → Branch protection rule para `main`:
- ✅ Require pull request reviews before merging (2 reviews)
- ✅ Require status checks to pass before merging (ci.yaml)
- ✅ Restrict who can push to matching branches

### 3. Teams (Microsoft Teams)
Canais a criar:
- #gestao-vulns-dev
- #gestao-vulns-security
- #gestao-vulns-blockers

---

**Status**: Setup em andamento
**Timeline**: Semana 1
