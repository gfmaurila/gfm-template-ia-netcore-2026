# Orientação para Claude Code

Leia `AGENTS.md` antes de qualquer tarefa. Ele contém as regras compartilhadas e prevalece sobre sugestões específicas desta ferramenta.

**IDIOMA OFICIAL: PORTUGUÊS BRASILEIRO (pt-BR).** Produza documentação, explicações, relatórios, critérios de aceite e respostas de trabalho em português brasileiro, salvo necessidade técnica ou solicitação explícita do usuário. Preserve nomes e identificadores técnicos.

- Use `.claude/rules/engineering.md` como índice complementar.
- Use agentes, comandos ou skills somente se estiverem disponíveis na versão instalada e se a tarefa justificar.
- Não presuma sintaxe ou capacidades de configuração não verificadas.
- Solicite aprovação do plano antes de alterar código ou infraestrutura.
- Preserve os limites de escopo, segurança, testes e evidências definidos em `AGENTS.md`.
- Selecione somente os módulos solicitados e aprovados: Back-end, Admin, Site, Landing Page, Mobile ou Full Stack; consulte `src/front-end/README.md` e os blueprints.
- Para Front-end, siga `docs/security/frontend-security.md`, `docs/testing/frontend-testing.md` e `docs/devops/frontend-devops.md`.
- Para fundação de projeto novo, consulte os modelos Fase 00 Back-end em `templates/tasks/bootstrap/back-end/` e siga o fluxo central de SPEC/PLAN/aprovação em `AGENTS.md`.

Os diretórios `.claude/agents`, `commands`, `rules` e `skills` desta fase contêm orientação documental, não automações executáveis.
