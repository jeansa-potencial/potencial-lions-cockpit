# Potencial & Lions | Partnership Cockpit

Sistema operacional cotidiano da parceria **Potencial & Lions**: converte decisões, compromissos e frentes em execução observável, auditável e evolutiva.

Este repositório é a **fonte técnica de verdade** (`GITHUB = APPLICATION / TECHNICAL TRUTH`). O estado operacional vivo (tarefas, prioridades, decisões) reside no **Notion** (`NOTION = OPERATIONAL TRUTH`) — este repositório nunca duplica esse estado, apenas o schema e o contrato que o governam.

## Missão e autoridade

Ver [`docs/mission-and-authority.md`](docs/mission-and-authority.md). Resumo: Business/Operations (autoridade de Jean) define regras de negócio; Application Engineering (Claude/Cowork, com Jean participando diretamente) implementa. As duas trilhas operam em paralelo sem tráfego administrativo — comunicação cross-boundary só ocorre por efeito material.

## Arquitetura

Frontend web → Google Apps Script (secure bridge/runtime) → Notion (backend operacional). Ver [`docs/architecture.md`](docs/architecture.md).

## Estrutura do repositório

```
potencial-lions-cockpit/
├── README.md
├── docs/
│   ├── mission-and-authority.md
│   ├── architecture.md
│   ├── requirements.md
│   ├── notion-data-model.md
│   ├── security.md
│   ├── change-protocol.md
│   ├── deployment.md
│   └── changelog.md
├── apps-script/        # runtime/secure bridge (Google Apps Script)
├── frontend/           # frontend web (evolução do protótipo de referência)
├── tests/              # planos e evidências de teste
├── releases/           # notas de release
└── provenance/         # pacote original recebido de Jean em 21/09/2026 (imutável, referência)
```

## Estado atual (21/09/2026)

- [x] Reconciliação do pacote técnico + protótipo de referência
- [x] Schema Notion v1 criado (Actions, Fronts, Decisions & Gates, Event Ledger)
- [x] Baseline de repositório e documentação técnica constituído
- [ ] Push para GitHub remoto — **pendente de acesso** (ver `docs/deployment.md`)
- [ ] Google Apps Script (secure bridge) — **pendente de autenticação clasp** (ver `docs/deployment.md`)
- [ ] Frontend conectado ao backend real
- [ ] Autenticação de produção definida
- [ ] Write / read-back / Event Ledger testados end-to-end

## Regras não-negociáveis (ver `docs/mission-and-authority.md` para o texto completo)

- Notion é o estado operacional canônico; GitHub é a verdade técnica.
- Nenhum secret no cliente (HTML/JS) ou neste repositório.
- Toda escrita material segue write → read-back → confirmação → Event Ledger antes de qualquer sucesso ser mostrado ao usuário.
- Regras de negócio não são inventadas nem alteradas pela camada de aplicação.
- Execução em Sprints, sem microaprovação entre fases internas.
