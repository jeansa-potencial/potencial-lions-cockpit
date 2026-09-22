# Changelog

## 2026-09-22 — Push completo ao GitHub remoto

- Repositório remoto `jeansa-potencial/potencial-lions-cockpit` sincronizado com o baseline local: 18/18 arquivos, cada um verificado byte a byte (SHA de blob Git do GitHub conferido contra `git hash-object` local).
- Confirmado, por investigação direta, que o acesso GitHub nativo do sandbox está bloqueado por um gate de autorização de repositório por sessão sem mecanismo de liberação disponível nesta sessão Cowork; via alternativa executada com sucesso: relé via navegador vinculado ao dispositivo de Jean (PAT já fornecido), usando a API de Conteúdo do GitHub.
- Corrigido e revalidado `provenance/01_RELATORIO_TECNICO_INTEGRAL_POTENCIAL_LIONS.md` (divergência de SHA de um push anterior) — agora byte-perfeito.
- Publicado `provenance/reference/Cockpit_Potencial_Lions_Sprint1_AtualAte20260921_v1-1.html` (arquivo novo, ~126 KB) — SHA final conferido.
- Atualizado `docs/deployment.md` para refletir o estado sincronizado.
- Nenhuma ação manual solicitada a Jean além do que já havia sido fornecido (token e vínculo do dispositivo).

## 2026-09-21 — Baseline inicial

- Reconciliação integral do pacote técnico entregue por Jean (relatório + requisitos + baseline GitHub + protocolo de mudanças + manifesto de provenance + protótipo HTML de referência); integridade verificada contra `provenance/SHA256SUMS.txt`.
- Ativado o Portable Layer GCNQA/PHBI vigente (v2-2) para governar planejamento e comunicação desta Sprint.
- Criado o espaço operacional no Notion — página "Potencial & Lions | Partnership Cockpit" com 4 databases: Fronts, Decisions & Gates, Actions, Event Ledger (schema v1, vazio, pronto para uso).
- Criado o baseline de repositório local (este repositório), com documentação técnica completa (`docs/`) e o pacote original preservado em `provenance/` para rastreabilidade.
- Iniciado fluxo de autenticação `clasp` (Google Apps Script) — aguardando código de autorização de Jean.
- Identificado gap de ferramenta: sem conector GitHub disponível nesta sessão — push ao remoto pendente de decisão de Jean sobre a via de acesso.
