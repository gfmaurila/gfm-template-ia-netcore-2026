# TASK-BE-011 — Observabilidade

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir sinais e operação diagnóstica adequados ao serviço.

## Cenários aplicáveis
Todo serviço operado; logs/métricas/tracing/integridade conforme NFRs, não por adoção automática de fornecedor.

## Pré-requisitos e dependências
BE-000, BE-002, BE-003; incident/SLO requirements quando existirem.

## Entradas necessárias
Fluxos críticos, owners, operação, SLO/alertas se definidos, classificação de dados e retenção.

## Escopo autorizado
Documentar telemetry contract e runbook; não enviar dados a serviços ou provisionar collector.

## Atividades futuras
Definir structured logs, metrics, distributed tracing, correlation IDs, integridade/prontidão (readiness)/liveness, alert thresholds e dashboard responsabilidade.

## Entregáveis esperados
Catálogo de sinais, política de retenção/acesso/mascaramento e critérios de prontidão (readiness).

## Critérios de aceite
Falhas diagnosticáveis; correlation sem segredo/PII; integridade não expõe informações; alerts têm responsável/ação e limiar justificado.

## Testes obrigatórios aplicáveis
Testar prontidão (readiness)/liveness, mascaramento e falhas observáveis; validar que integridade endpoints não vazam detalhes.

## Segurança
Minimizar/coletar somente necessário; controle de acesso; evitar carga útil (payload)/token/password/connection strings nos logs.

## Evidências exigidas
Catálogo revisado, teste de mascaramento/integridade futuro e runbook linkado.

## Riscos
Ruído/custo alto, dados sensíveis ou ausência de alerta acionável.

## Critérios de conclusão
Cobertura de operação aprovada e telemetria segura; não aplicável deve ser justificado.
