# Missão e Modelo de Autoridade

Fonte: `provenance/01_RELATORIO_TECNICO_INTEGRAL_POTENCIAL_LIONS.md` (documento canônico entregue por Jean em 21/09/2026). Este arquivo resume; em caso de divergência, o documento em `provenance/` prevalece.

## Problema

A parceria Potencial & Lions carece de uma superfície única, persistente e auditável para saber o que importa agora, quem precisa agir, o que está bloqueado, o que depende de decisão e o que foi concluído — sem depender de memória individual ou reconstrução manual de contexto.

## Missão

Construir e **operar** um sistema cotidiano de coordenação da parceria que converta decisões, compromissos e frentes em execução observável, com responsabilidade clara, persistência, histórico e capacidade de evolução.

## Duas trilhas — parallel ownership + material boundary communication

| Trilha | Autoridade | Escopo |
|---|---|---|
| Business/Operations | Jean (aprovação final) | Regras de negócio, semântica dos controles, prioridades empresariais, accountability |
| Application Engineering | Claude/Cowork, com Jean participando diretamente | Arquitetura técnica, frontend, Google Apps Script, integração Notion, autenticação, segurança, testes, deployment, GitHub |

**Regra de fronteira:** Application Engineering não inventa nem altera regra de negócio. Se uma limitação técnica tornar uma regra aprovada inviável, a decisão é isolada e levada a Jean — nunca redefinida silenciosamente.

**Regra contra comunicação administrativa:** não há tráfego de status entre trilhas/IAs. Comunicação cross-boundary só ocorre por efeito material sobre requisito, regra, infraestrutura, risco, dado, segurança ou critério de aceite.

## Business Rules protegidas (não alteráveis sem aprovação de Jean)

| ID | Regra |
|---|---|
| BR-001 | Identidade institucional do produto é "Potencial & Lions"; Jean/Marina são responsáveis individuais, não o nome do produto |
| BR-002 | Regras de negócio, semântica de controles e prioridades dependem de aprovação de Jean |
| BR-003 | Sem tráfego administrativo inter-IA |
| BR-004 | Notion é a verdade operacional |
| BR-005 | GitHub é a verdade técnica |
| BR-006 | Sucesso material só é reportado após confirmação do estado persistido (write → read-back) |
| BR-007 | Uma Sprint pode conter várias fases internas sem microaprovação; para apenas em boundary material |

Requisitos funcionais, não-funcionais, técnicos e critérios de aceite completos: `provenance/02_REQUISITOS_E_CRITERIOS_DE_ACEITE.md`.
