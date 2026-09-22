# Requisitos e Critérios de Aceite — Potencial & Lions | Partnership Cockpit

## 1. Classificação de requisitos

- `BR-*` — Business Rule: não alterar sem Human Authority.
- `FR-*` — Functional Requirement: comportamento esperado do produto.
- `NFR-*` — Non-Functional Requirement: qualidade, segurança e operação.
- `TR-*` — Technical Requirement: boundary técnico obrigatório.
- `AC-*` — Acceptance Criterion: teste verificável.

## 2. Business Rules protegidas

### BR-001 — Identidade
A identidade institucional do produto é **Potencial & Lions**. Jean e Marina podem aparecer como responsáveis individuais, não como nome institucional do produto.

### BR-002 — Business Authority
Regras de negócio, semântica dos controles, prioridades empresariais e comportamento que altere a operação real dependem de aprovação de Jean.

### BR-003 — No Administrative Inter-AI Traffic
Business/Operations e Application Engineering trabalham em paralelo. Comunicação cross-boundary ocorre somente por mudança material de requisito, regra, infraestrutura, risco, segurança, dado ou critério de aceite.

### BR-004 — Notion Operational Truth
O estado operacional canônico da aplicação reside no Notion.

### BR-005 — GitHub Technical Truth
Código e documentação técnica material da aplicação devem ser persistidos no GitHub.

### BR-006 — Material Success Requires Confirmation
Uma alteração material só é apresentada como concluída após confirmação do estado persistido.

### BR-007 — Sprint Integrity
Uma Sprint pode conter várias fases internas executadas sem microaprovação. Parada somente em boundary material.

## 3. Functional Requirements

### FR-001 — Login / access gate
A aplicação deve impedir acesso a dados protegidos antes da autenticação/autorização.

### FR-002 — Current snapshot
Carregar dados atuais do backend e indicar estado de carregamento/erro.

### FR-003 — Executive view
Exibir indicadores/pressões úteis à condução da parceria sem depender de leitura de todas as tarefas.

### FR-004 — Agora
Exibir fila priorizada conforme regra de negócio aprovada e explicar os fatores de prioridade quando material.

### FR-005 — Tasks
Permitir pesquisar, filtrar, abrir detalhe e executar atualizações autorizadas.

### FR-006 — Owners
Permitir visualizar distribuição por responsável e identificar accountability.

### FR-007 — Fronts
Permitir visão e filtragem por frente.

### FR-008 — Decisions & Gates
Distinguir itens decisórios de tarefas e preservar seus limites de autoridade.

### FR-009 — Create action
Permitir criação com campos obrigatórios e validação.

### FR-010 — Update action
Permitir mudanças permitidas de status, prioridade, responsável e outros campos aprovados.

### FR-011 — Evidence reference
Permitir associar referência/evidência quando a regra do objeto exigir.

### FR-012 — Event ledger
Registrar mudanças materiais e permitir reconstrução mínima do evento.

### FR-013 — Logout/session termination
Permitir encerramento efetivo da sessão conforme o mecanismo de autenticação.

## 4. Non-Functional Requirements

### NFR-001 — Security
Nenhum secret de integração pode ser enviado ao cliente ou versionado no GitHub.

### NFR-002 — Honesty of state
A interface não pode exibir sucesso que não tenha sido confirmado pelo backend.

### NFR-003 — Responsiveness
Desktop e mobile devem manter funções essenciais utilizáveis.

### NFR-004 — Low friction
Fluxos recorrentes devem exigir o mínimo de etapas razoável.

### NFR-005 — Recoverability
A aplicação deve poder ser compreendida e reconstruída a partir de GitHub + configurações seguras + backend, sem depender de transcript de IA.

### NFR-006 — Documentation parity
Mudanças técnicas materiais exigem atualização da documentação afetada.

### NFR-007 — Observability
Falhas devem gerar informação suficiente para diagnóstico sem vazar secrets.

### NFR-008 — Accessibility semantics
Estados críticos não dependem apenas de cor; labels, texto e foco devem permanecer claros.

### NFR-009 — Minimal infrastructure
Não adicionar serviço novo sem necessidade material demonstrável.

## 5. Technical Requirements

### TR-001 — Apps Script baseline
Usar Google Apps Script como runtime/host/bridge de baseline.

### TR-002 — Server-side Notion access
Notion token/credential deve permanecer server-side.

### TR-003 — Structured API contract
Frontend e backend devem trocar comandos/respostas estruturados e versionáveis.

### TR-004 — Write/read-back
Toda escrita material deve ser seguida por read-back da entidade/estado relevante.

### TR-005 — Event recording
Após confirmação de mudança material, registrar evento conforme modelo do Event Ledger.

### TR-006 — Idempotency / duplicate protection
Operações suscetíveis a repetição devem ser protegidas proporcionalmente contra duplicidade/replay.

### TR-007 — GitHub repository
Persistir código, docs, testes e release history no GitHub; usar `.gitignore` e secret discipline.

### TR-008 — Prototype migration
O HTML atual é referência de UX, não base de segurança. Remover credenciais demo e `localStorage` como fonte canônica de produção.

## 6. Acceptance tests

### AC-001 — Unauthorized access
**Given** usuário não autorizado  
**When** solicita snapshot protegido  
**Then** nenhuma informação operacional é retornada.

### AC-002 — Authorized snapshot
**Given** usuário autorizado  
**When** abre o Cockpit  
**Then** recebe estado atual do Notion e as visões principais carregam sem depender de dados demo.

### AC-003 — Status update success
**Given** usuário autorizado e transição permitida  
**When** altera status  
**Then** write ocorre, read-back confirma, Event Ledger registra e UI mostra sucesso com estado confirmado.

### AC-004 — Write failure
**Given** falha de Notion/API  
**When** usuário solicita mudança  
**Then** UI não mostra sucesso e preserva clareza sobre o estado não confirmado.

### AC-005 — Read-back mismatch
**Given** write retorna resposta mas read-back não confirma o estado esperado  
**When** backend valida resultado  
**Then** resposta é erro/estado inconsistente e exige tratamento, não sucesso.

### AC-006 — Duplicate request
**Given** requisição material repetida  
**When** a mesma operação é reenviada  
**Then** não cria efeito duplicado indevido.

### AC-007 — Session end
**Given** usuário autenticado  
**When** faz logout  
**Then** operações protegidas exigem nova autenticação.

### AC-008 — Secret scan
**Given** release candidate  
**When** repositório e bundle cliente são inspecionados  
**Then** nenhum token/senha real/secret de produção está presente.

### AC-009 — GitHub recoverability
**Given** novo mantenedor autorizado  
**When** acessa o repositório  
**Then** consegue identificar missão, arquitetura, setup, testes, deployment e changelog sem transcript anterior.

### AC-010 — Mobile core flow
**Given** viewport mobile  
**When** usuário autentica, abre Agora, abre tarefa e atualiza campo permitido  
**Then** fluxo permanece legível e utilizável.

### AC-011 — Business-rule protection
**Given** requisito técnico ambíguo que alteraria semântica de negócio  
**When** Cowork identifica a ambiguidade  
**Then** não inventa a regra; isola a decisão para Human Authority.

### AC-012 — No administrative dependency
**Given** uma fase técnica concluída dentro da Sprint  
**When** próxima fase pode avançar com autoridade existente  
**Then** Cowork avança sem exigir mensagem administrativa de outra IA.

## 7. Release gate

Release só pode ser considerado pronto quando:

- todos os ACs aplicáveis passaram ou possuem exceção material registrada;
- código/documentação estão no GitHub;
- deployment foi verificado;
- Notion integration foi validada;
- autenticação/autorização foram testadas;
- write/read-back/ledger foram testados;
- desktop/mobile essenciais foram validados;
- não há secrets no cliente/repositório;
- não há false success conhecido;
- nenhuma regra de negócio foi alterada silenciosamente.

