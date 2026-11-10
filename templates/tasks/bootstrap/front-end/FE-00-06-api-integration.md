# FE-00-06 — Definir integração com APIs

- **Objetivo:** definir contratos, cliente, validação e falhas para cada API consumida.
- **Dependências:** contrato/spec da API aprovado e FE-00-02.
- **Escopo:** mapear operações, esquemas, autenticação, tempo limite (timeout), cancelamento, nova tentativa (retry) seguro, cache e versionamento. Não gerar cliente/código.
- **Responsável/agente/status:** [preencher] / Pendente
- **Segurança:** tratar resposta como não confiável; sem segredo no bundle; autorização na API; redigir PII.
- **Validações/evidências:** matriz endpoint→feature, contrato versionado, casos de erro e compatibilidade.
- **Aceite:** comportamento offline/falha/nova tentativa (retry) e validação runtime definidos; operações destrutivas não são repetidas sem idempotência.
