# Blueprint: API + Worker + Batch

## Objetivo
Combinar entrada síncrona, processamento contínuo assíncrono e operação finita/administrativa.

## Quando utilizar / quando não utilizar
Utilizar somente quando existirem os três perfis operacionais. Não separar batch ou worker por antecipação; manter caso de uso único em Application.

## Projetos futuros e dependências
`API`, `Worker` e `Batch` são hosts separados sobre Application/Domain/Core. Infrastructure contém adaptadores e persistência. CrossCutting é opcional para composição. API/Worker/Batch não dependem uns dos outros.

## Organização de classes
API submete/consulta; Worker processa mensagens; Batch executa tarefa finita com checkpoint e execução simulada (dry-run) quando apropriado. Manipuladores e regras ficam em Application/Domain; transporte e armazenamento em Infrastructure.

## Segurança e persistência
Identidades distintas por host, menor privilégio, autorização por recurso/operação, configuração por ambiente e segredos em vault. Banco com responsabilidade/transações; batch restrito por janela/escopo; outbox/inbox e idempotência para mensageria.

## Testes, Docker e CI/CD
Testes unitários compartilhados; testes de integração por adaptador/host em infraestrutura descartável; contratos HTTP/mensagem e E2E de jornada. Imagens por host quando necessário; pipelines independentes de compilação, mas gates comuns.

## Observabilidade e diagramas
Correlação ponta a ponta, métricas por host, status de batch, atraso, novas tentativas e falhas. Draw.io inclui C4, sequência API→Worker, operação Batch e implantação.

## Plano, tarefas e critérios de aceite
Mapear responsabilidade, contrato e ciclo de vida; planejar status/nova tentativa (retry)/reconciliação; separar tarefas sem duplicar regra. Criar runbooks de replay, batch e reversão (rollback).

Aceite: cada host tem finalidade clara; não há dependência entre hosts em runtime sem contrato; tarefas são idempotentes e auditáveis; testes cobrindo interações; todos os hosts têm segurança, integridade e operação documentados.
