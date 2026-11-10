# TASK-BE-014 — Mensageria

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Planejar mensageria somente quando desacoplamento assíncrono for requisito.

## Cenários aplicáveis
Condicional. Se não há necessidade de broker, registrar não aplicabilidade e não adicionar infraestrutura.

## Pré-requisitos e dependências
BE-002 (arquitetura), BE-003 (config/identidade) e BE-008 (modelo de ameaças); SPEC/PLAN aprovados.

## Entradas necessárias
Semântica entrega/ordem, vazão (throughput), latência, retenção, partições, contract/version, ack/offset, nova tentativa (retry)/DLQ, responsabilidade e recuperação.

## Escopo autorizado
Definir arquitetura/contratos e teste futuro; sem broker, produtor/consumidor ou infraestrutura implementados.

## Atividades futuras
Separar Domain Events, Integration Events/contracts, manipuladores, producers/consumers; avaliar Outbox/Inbox; definir idempotência, nova tentativa (retry)/espera exponencial (backoff), DLQ/replay, offset/ack, observabilidade e broker temporário.

## Entregáveis esperados
ADR/contratos versionados, sequence/falha diagramas, matrizes de garantias e runbook.

## Critérios de aceite
Broker justificado; manipuladores idempotentes; ack após efeito durável; nova tentativa (retry)/DLQ/replay e ordenação definidos; falhas não parecem sucesso.

## Testes obrigatórios aplicáveis
Unit/contract/integration com broker temporário; duplicidade, ordem, nova tentativa (retry), tempo limite (timeout), DLQ, replay e limpeza conforme semântica.

## Segurança
TLS/autenticação, ACL least privilege, segredo management, carga útil (payload) minimizado/redacted, retenção/classification definidos.

## Evidências exigidas
Testes de contrato, broker integration results, idempotency/replay proof, telemetry/limpeza e revisão de segurança.

## Riscos
Message loss/duplication, poison messages, consumidor lag, esquema breakage ou offset commit prematuro.

## Critérios de conclusão
Decisão/aplicabilidade aprovada e todos os gates específicos atendidos; se não aplicável, justificativa registrada.
