# Blueprint: Worker

## Objetivo
Hospedar processamento contínuo, consumo de mensagens ou tarefas recorrentes sem expor API pública desnecessária.

## Quando utilizar / quando não utilizar
Utilizar para trabalho assíncrono contínuo, filas, schedules ou processamento desacoplado. Não criar worker quando uma chamada síncrona curta atende ao requisito; não usar Worker para duplicar lógica de negócio.

## Projetos futuros e dependências
`GFM.Template.Worker` é host/composition root e chama Application. Infrastructure implementa transportes. Application -> Domain/Core; Domain -> Core. Worker não define port/adaptador de banco/broker.

## Organização de classes
Hosted service fino; consumidor/adaptador recebe carga útil (payload), valida contrato, cria escopo e invoca caso de uso. Manipuladores em Application. Configuração/options tipadas e ciclo de vida/cancellation gerenciados pelo host.

## Segurança e persistência
Identidade de serviço de menor privilégio; segredo por vault; TLS validado; dados minimizados em logs. Definir commit/ack somente após resultado durável; transação, nova tentativa (retry), espera exponencial (backoff), tempo limite (timeout), DLQ e idempotência explícitos.

## Testes, Docker e CI/CD
Testes unitários de casos/manipuladores; IntegrationTests com broker e armazenamento descartáveis via Testcontainers quando apropriado; ContractTests para mensagens; teste de idempotência/nova tentativa (retry). Container não privilegiado, verificações de integridade (health checks) e encerramento gracioso; CI testa todos os gates.

## Observabilidade e diagramas
Métricas de mensagens recebidas/processadas/falhas/retentativas/lag; correlation/trace IDs; alertas sem carga útil (payload). Draw.io: sequência mensagem→manipulador→persistência/ack, C4 e zonas de confiança.

## Plano, tarefas e critérios de aceite
Especificar tópico/contrato, semântica de entrega, ordenação, vazão (throughput), reprocessamento e operação. Tarefas aprovadas cobrem adaptador, manipulador, persistência, nova tentativa (retry)/DLQ, observabilidade e testes.

Aceite: falhas não são confirmadas como sucesso; reprocessamento idempotente; DLQ/replay definidos; cancelamento gracioso; segredos e carga útil (payload) sensível ausentes de logs; testes de integração aprovados.
