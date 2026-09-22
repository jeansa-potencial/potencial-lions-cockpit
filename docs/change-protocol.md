# Protocolo de Mudanças Materiais

Fonte completa: `provenance/04_PROTOCOLO_DE_MUDANCAS_MATERIAIS.md`.

Princípio: **parallel ownership + material boundary communication**. As trilhas não trocam mensagens administrativas.

## Business → Technical (objeto de mudança)

Deve conter: Change ID, objeto afetado, motivo, comportamento anterior, novo comportamento aprovado, impacto de dados, impacto de UX, compatibilidade/migração, critérios de aceite, prioridade, aprovação/provenance.

## Technical → Business (escalada, apenas quando inevitável)

Exemplos: limitação de plataforma torna regra aprovada impossível; requisito de segurança muda responsabilidade do usuário; restrição de dados elimina auditabilidade; restrição de deployment/acesso muda população de acesso; simplificação proposta removeria um controle material.

## Não criar

Pedidos de status, confirmações de recebimento sem efeito material, handoffs administrativos por fase, mensagens "continuamos trabalhando", dependência de resposta de outro ambiente para prosseguir em tarefa independente.
