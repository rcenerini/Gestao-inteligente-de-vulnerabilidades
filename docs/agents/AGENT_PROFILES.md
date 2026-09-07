# Perfis de Agents - SSCV

## Propósito
Documentar agents AI que auxiliam em diferentes fases do desenvolvimento e operação do SSCV.

## Agents Implementados

### 1. Vulnerability Analyzer Agent
- **Responsabilidade**: Análise de vulnerabilidades de APIs Tenable/Qualys
- **Input**: Dados brutos de vulnerabilidades
- **Output**: Insights estruturados com priorização
- **Owner**: Security Team

### 2. Remediation Orchestrator Agent
- **Responsabilidade**: Coordenar remediação automática
- **Input**: Vulnerabilidades priorizadas
- **Output**: Plano de ação executável
- **Owner**: DevOps Team

### 3. Compliance Monitor Agent
- **Responsabilidade**: Validar conformidade com frameworks (OWASP, CIS, PCI-DSS)
- **Input**: Estado da infraestrutura
- **Output**: Relatórios de compliance e gaps
- **Owner**: Compliance Team

### 4. Incident Response Agent
- **Responsabilidade**: Escalação e gerenciamento de incidentes críticos
- **Input**: Eventos de segurança críticos
- **Output**: Notificações no Teams + plano de resposta
- **Owner**: Security Ops

---

**Próximas Etapas**: Definir prompts, integrations e SLAs para cada agent
