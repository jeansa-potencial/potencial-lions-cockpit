# Modelo de Dados Notion (v1 — materializado em 21/09/2026)

Espaço criado: **Potencial & Lions | Partnership Cockpit**
`https://app.notion.com/p/3e3162caf08d8196ba5de27b55ca8715`

Este schema é v1 (baseline funcional para a Sprint inicial) — evolutivo por design (RNF-08). Alteração de significado de campo é mudança de negócio (requer aprovação de Jean); alteração puramente técnica de schema é responsabilidade de engenharia (Seção 20.2 do relatório).

## Fronts
`https://app.notion.com/p/7b8a6aca18e6425090860dd921c1cbe1` — data source `b087f1e3-c101-49a5-a785-ed267c89f461`

| Campo | Tipo |
|---|---|
| Frente (title) | Título |
| Descrição | Texto |
| Status | Select (Ativa / Pausada / Encerrada) |
| Owner (Potencial) | Texto |
| Owner (Lions) | Texto |

## Decisions & Gates
`https://app.notion.com/p/a03a69da8eea4dca8f6cc5895f297a8c` — data source `c1a42d23-9642-44e2-be77-bef7aae1dd3f`

| Campo | Tipo |
|---|---|
| Decisão / Gate (title) | Título |
| Descrição | Texto |
| Status | Status (Not started / In progress / Done) |
| Autoridade requerida | Select (Jean / Business-Operations / Application Engineering / Conjunta) |
| Frente | Relation → Fronts (dual) |
| Prazo/janela | Data |
| Decisão registrada | Texto |
| Impacto se não decidido | Texto |

## Actions
`https://app.notion.com/p/31f31e3fc5964db4a767fdbe80f3ff07` — data source `5ff7e5df-2831-440b-8728-e7a44aa666e1`

Campos mínimos recomendados pela Seção 7.1 do relatório, materializados:

| Campo | Tipo | Nota |
|---|---|---|
| Ação / Título (title) | Título | |
| Action ID | Unique ID (prefixo `PLA`) | prefixo `ACT` já em uso por outro cockpit de Jean no mesmo workspace |
| Frente | Relation → Fronts (dual) | |
| Decisão/Gate relacionado | Relation → Decisions & Gates (dual) | |
| Responsável | Pessoa (Notion person) | |
| Prioridade | Select (Urgente / Importante / Pendente / Delegável / Aguardando terceiros) | reflete a classificação padrão de Jean |
| Status | Status (Not started / In progress / Done) | evoluir para estados mais granulares na Sprint 2 se necessário |
| Prazo/janela | Data | |
| Próximo passo | Texto | |
| Definition of Done | Texto | |
| Origem/Provenance | Select (Relatório técnico / Business-Operations / Application Engineering / Decisão de Jean) | |
| Evidence Ref | URL | |
| Atualizado em | Last edited time (automático) | |
| Atualizado por | Texto | preenchido pelo Apps Script na Sprint 2; sem "last edited by" nativo neste schema |

## Event Ledger
`https://app.notion.com/p/06a95cb3372943efaaef208677747d9c` — data source `0f009669-93a1-4bf1-bcee-543e153704f8`

| Campo | Tipo |
|---|---|
| Evento (title) | Título |
| Timestamp | Created time (automático) |
| Action relacionada | Relation → Actions (dual) |
| Decisão/Gate relacionado | Relation → Decisions & Gates (dual) |
| Tipo de mudança | Select (mudança de status / prioridade / responsável / conclusão / cancelamento / decisão-gate / evidência-provenance) |
| Estado anterior | Texto |
| Estado novo | Texto |
| Ator | Texto |
| Evidência | URL |

## Pendências deste schema (Sprint 2)

- Nenhum registro de exemplo foi criado ainda — schema vazio, pronto para população real ou de teste.
- Escrita/leitura será feita pelo Apps Script via API do Notion (token server-side, nunca no cliente) — não pelo conector Cowork em produção.
- Considerar campo "Última confirmação (read-back)" em Actions quando o contrato de persistência (TR-004) for implementado.
