# Arquitetura Técnica

## Baseline aprovado

```
Potencial & Lions Users → Frontend Web → Google Apps Script (Secure Bridge) → Notion (Operational Backend)
                                                     ↓
                                         Event/Technical Logging
Claude/Cowork ↔ GitHub Repository (este repositório)
```

O browser nunca recebe segredo de integração do Notion. Apps Script é o runtime permanente e a camada de mediação. Notion guarda o estado operacional; GitHub guarda o estado técnico/documental.

## Componentes

- **Frontend:** apresenta estado operacional, recebe interações, valida campos básicos, nunca afirma sucesso material antes de confirmação server-side, responsivo em desktop e mobile.
- **Google Apps Script:** hospeda o Web App (`doGet`/`doPost`), mantém secrets/config server-side (Script Properties), autentica/autoriza requisições, acessa Notion, executa read/write, faz read-back, aplica idempotência quando necessário, registra eventos, devolve respostas estruturadas.
- **Notion:** fonte canônica de estado operacional (`NOTION = OPERATIONAL TRUTH`). Schema documentado em `docs/notion-data-model.md`.
- **GitHub:** fonte persistente de verdade técnica/documental (`GITHUB = APPLICATION / TECHNICAL TRUTH`).

## Distinção canônica

| Objeto | Fonte canônica |
|---|---|
| Status de uma Action | Notion |
| Responsável operacional | Notion |
| Decisão/gate registrado | Notion |
| Código Apps Script | GitHub |
| Frontend source | GitHub |
| Arquitetura técnica | GitHub (este diretório `docs/`) |
| Regra de negócio aprovada | Business/Operations (Jean) + `docs/mission-and-authority.md` |
| Secret/token | Secret store server-side (Script Properties) — nunca Git/cliente |

## Contrato de persistência (obrigatório para toda mudança material)

```
User → Frontend: solicita mudança
Frontend → Apps Script: comando estruturado
Apps Script: valida autorização e regra técnica
Apps Script → Notion: write
Notion → Apps Script: resposta da escrita
Apps Script → Notion: read-back
Notion → Apps Script: estado confirmado
Apps Script → Event Ledger: registra evento material
Apps Script → Frontend: sucesso + estado confirmado
Frontend → User: atualiza interface
```

Se o read-back falhar, o sistema informa estado incerto/erro — nunca "false success" (RF-09, NFR-002, TR-004).

## Prototype como referência de UX (não de produção)

`provenance/reference/Cockpit_Potencial_Lions_Sprint1_AtualAte20260921_v1-1.html` define navegação, visões (Executiva, Agora, Tarefas, Responsáveis, Frentes, Decisões & Gates, Deltas) e comportamento esperado. Usa login demo (`jean/demo`, `marina/demo`) e `localStorage` — ambos devem ser removidos na produção (TR-008).
