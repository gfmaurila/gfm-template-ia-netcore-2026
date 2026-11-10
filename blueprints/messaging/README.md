# Blueprint: Mensageria

## Objetivo
Desacoplar produtores e consumidores com processamento assíncrono e semântica de entrega definida.

## Quando utilizar / quando não utilizar
Utilizar para desacoplamento temporal, vazão (throughput) variável ou fan-out que justifique broker. Não usar para chamadas simples síncronas sem necessidade assíncrona.

## Projetos futuros e dependências
Contratos genéricos/envelope ficam no Core; evento específico de domínio em Domain; integração versionada em módulo/contrato compartilhado; manipuladores e orquestração em Application; broker/outbox/inbox em Infrastructure; Worker hospeda consumo.

## Organização de classes
Serializers e adaptadores; produtor/consumidor finos; manipulador chama caso de uso. Transporte não contém regra; Worker não reimplementa Kafka client.

## Segurança e persistência
TLS e autenticação do broker; ACL por tópico; retenção e classificação; redigir carga útil (payload). Confirmar offset somente após efeito durável. Usar outbox/inbox, idempotência persistente, nova tentativa (retry) com espera exponencial (backoff), DLQ e replay controlado conforme garantias.

## Testes, Docker e CI/CD
Unit test manipuladores; contract/esquema tests; IntegrationTests com broker Testcontainers descartável; duplicidade, ordenação, tempo limite (timeout), DLQ e nova tentativa (retry). Docker local opcional e CI reproduzível.

## Observabilidade e diagramas
Lag, vazão (throughput), falhas, novas tentativas (retries), DLQ e idade de mensagens; correlation IDs e spans. Draw.io: sequência produtor/outbox/broker/consumidor/ack e fluxos de erro.

## Plano, tarefas e critérios de aceite
Decidir entrega, ordem, partição, compatibilidade, retenção, nova tentativa (retry) e operação. Criar tarefas para contratos, produtor, consumidor, armazenamento, DLQ e testes.

Aceite: contrato versionado; manipulador idempotente; falha não é sucesso; redrive controlado; segurança e observabilidade configuradas; integração testada sem broker compartilhado.
