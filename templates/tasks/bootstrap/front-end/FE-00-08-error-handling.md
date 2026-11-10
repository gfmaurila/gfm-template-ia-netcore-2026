# FE-00-08 — Definir tratamento de erros

- **Objetivo:** padronizar estados de erro, loading, vazio e recuperação na experiência.
- **Dependências:** FE-00-02 e FE-00-06 quando há API.
- **Escopo:** classificar validação, rede, autenticação, servidor, offline e inesperado; definir mensagens, nova tentativa (retry) e correlation. Não codificar manipuladores.
- **Responsável/agente/status:** [preencher] / Pendente
- **Segurança:** não revelar stack trace, tokens, payloads, PII ou detalhes internos; erros não mascaram falhas críticas.
- **Validações/evidências:** matriz erro→UX→telemetria→recuperação e cenários de teste.
- **Aceite:** falhas são explícitas e acessíveis; nova tentativa (retry) é segura/idempotente; telemetria sem dados sensíveis.
