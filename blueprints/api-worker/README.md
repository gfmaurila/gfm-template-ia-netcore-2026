# Blueprint: API + Worker

## Objetivo
Aceitar uma solicitação HTTP e processar trabalho longo de modo assíncrono, com estado e resultado consultáveis.

## Quando utilizar / quando não utilizar
Utilizar quando duração, nova tentativa (retry), vazão (throughput) ou disponibilidade do consumidor não cabem no requisição. Não adicionar fila a operação curta sem necessidade, nem responder aceite antes de persistir trabalho duravelmente.

## Projetos futuros e dependências
API e Worker são hosts distintos sobre Application/Domain/Core; Infrastructure implementa banco, broker e Outbox. CrossCutting opcional fica na composição; nenhuma dependência Application → Infrastructure/CrossCutting.

## Organização de classes
A API valida a requisição e inicia um caso de uso; o status/ID é retornado; a outbox publica um evento de integração; o Worker consome o evento e chama um manipulador da Application; a API de consulta expõe o status. Domain Events não são publicados diretamente como contratos.

## Segurança e persistência
Autenticação, autorização do recurso/tenant, idempotência persistente, proteção contra replay, carga útil (payload) minimizado. Persistir status/outbox atomicamente; consumidor com Inbox/unique key, nova tentativa (retry) e DLQ.

## Testes, Docker e CI/CD
Testes unitários para submissão/manipulador; testes de integração com banco/broker descartáveis; ContractTests para API/evento; E2E para jornada crítica. Imagens separadas somente se hosts diferentes; pipeline testa ambos.

## Observabilidade e diagramas
Correlacionar requisição e mensagem; medir fila/latência total/status/nova tentativa (retry). Draw.io sequência requisição→DB/outbox→broker→Worker→resultado e diagrama de implantação.

## Plano, tarefas e critérios de aceite
Definir máquina de estados, tempo limite (timeout), cancelamento, expiração, reprocessamento e consulta. Tarefas de API, outbox, consumidor, idempotência, testes e runbook.

Aceite: aceite HTTP somente após persistência durável; nova tentativa (retry) não duplica efeito; cliente consulta resultado autorizado; falha visível e recuperável; jornada coberta por integração.
