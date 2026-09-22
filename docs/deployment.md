# Deployment

## Estado em 21/09/2026

| Componente | Estado | Bloqueio |
|---|---|---|
| Repositório GitHub remoto | Não criado | Aguardando via de acesso (conector GitHub para esta sessão, ou token) |
| Google Apps Script (projeto + deploy) | Não criado | Aguardando autenticação `clasp` (fluxo iniciado — ver abaixo) |
| Notion (schema operacional) | **Criado** | — |
| Repositório local (este diretório) | **Criado, versionado localmente** | Pronto para push assim que o remoto existir |

## GitHub

Nenhum conector GitHub está disponível nesta sessão Cowork, e a busca no registro de conectores MCP (`github`, `git repository`) não retornou um conector instalável para GitHub. Vias possíveis, em ordem de preferência:

1. Jean habilita um conector GitHub em Configurações → Conectores do Cowork, se existir um disponível para a organização.
2. Alternativa imediata: Jean cria um repositório vazio (ex.: `potencial-lions-cockpit`) e gera um **fine-grained Personal Access Token** com escopo restrito a esse repositório (permissão de conteúdo: leitura/escrita). O token é usado apenas nesta sessão para `git push`, nunca commitado, e pode ser revogado depois do push inicial.

## Google Apps Script (clasp)

Fluxo de autorização iniciado nesta sessão (processo `clasp login --no-localhost` ativo, aguardando o código de retorno do OAuth). Após Jean autorizar no navegador e colar a URL de retorno na conversa, a sessão fica autenticada como a conta Google de Jean, com escopo para criar/gerenciar projetos e deployments de Apps Script.

Nenhum secret desse fluxo é commitado neste repositório (ver `.gitignore` — `.clasprc.json`).
