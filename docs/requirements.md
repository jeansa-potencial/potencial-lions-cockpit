# Requisitos e Critérios de Aceite

Fonte canônica completa: `provenance/02_REQUISITOS_E_CRITERIOS_DE_ACEITE.md` (não duplicar aqui — este arquivo é apenas um índice de navegação).

- **BR-\*** (7 regras) — Business Rules, não alteráveis sem Jean.
- **FR-\*** (13 requisitos) — comportamento funcional esperado (auth, snapshot, busca/filtros, detalhe, atualização material, criação, decisões/gates, event ledger, logout, etc.).
- **NFR-\*** (9 requisitos) — segurança, honestidade de estado, responsividade, baixa fricção, recuperabilidade, documentação, observabilidade, acessibilidade, infraestrutura mínima.
- **TR-\*** (8 requisitos) — Apps Script baseline, acesso server-side ao Notion, contrato de API estruturado, write/read-back, event recording, idempotência, repositório GitHub, migração do protótipo.
- **AC-\*** (12 critérios) — testes de aceite verificáveis (acesso não autorizado, snapshot autorizado, sucesso de atualização, falha de escrita, mismatch de read-back, requisição duplicada, fim de sessão, secret scan, recuperabilidade via GitHub, fluxo mobile, proteção de regra de negócio, sem dependência administrativa).

## Release gate

Release só é considerado pronto quando: todos os ACs aplicáveis passaram (ou têm exceção material registrada); código/documentação estão no GitHub; deployment foi verificado; integração Notion validada; autenticação/autorização testadas; write/read-back/ledger testados; desktop/mobile essenciais validados; sem secrets no cliente/repositório; sem false success conhecido; nenhuma regra de negócio alterada silenciosamente.
