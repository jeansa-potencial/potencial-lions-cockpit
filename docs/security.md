# Segurança

Baseline mínimo exigido (Seção 13 do relatório técnico):

- Tokens do Notion nunca no HTML/JS cliente.
- Nenhuma senha real versionada no GitHub.
- Secrets fora do repositório (ver `.gitignore`).
- Validação server-side em toda operação material, não apenas no login.
- Sessões com expiração adequada; logout real.
- Proteção razoável contra tentativa repetida e replay (idempotência — TR-006).
- Logs sem vazamento de credenciais; mensagens de erro sem expor secrets.
- Menor privilégio possível para integrações (Notion, Google).
- Revisão de acesso antes de produção.

As credenciais de demonstração do protótipo (`jean/demo`, `marina/demo`) e o uso de `localStorage` como fonte de verdade **não** entram na produção (TR-008). O mecanismo de autenticação final de produção é uma decisão técnica em aberto (Seção 20.1 do relatório) — proposta a ser levada a Jean quando a fase "Secure Bridge" for implementada.

## Gestão de secrets neste projeto

- Token de integração Notion: Script Properties do Apps Script (server-side).
- Credencial de push ao GitHub: mantida apenas na sessão do operador que executa o push; nunca commitada; nunca escrita em `docs/`, `frontend/` ou `apps-script/`.
- Credencial `clasp`/Google (`~/.clasprc.json`): local à máquina/sessão que autentica; nunca commitada (ver `.gitignore`).
