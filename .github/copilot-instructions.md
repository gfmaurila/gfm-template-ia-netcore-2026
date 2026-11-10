# Instruções para GitHub Copilot

Leia e siga `AGENTS.md` como política central do repositório. Estas instruções são intencionalmente curtas para evitar divergência.

**IDIOMA OFICIAL: PORTUGUÊS BRASILEIRO (pt-BR).** Produza documentação, explicações, relatórios, critérios de aceite e respostas de trabalho em português brasileiro, salvo necessidade técnica ou solicitação explícita do usuário. Preserve nomes e identificadores técnicos.

- Entenda os limites da tarefa antes de propor ou fazer alterações.
- Para trabalho futuro em código, apresente especificação, arquitetura, plano e tarefas dependentes; aguarde aprovação explícita antes da implementação.
- Preserve as regras em `governance/` e os Quality Gates aplicáveis.
- Selecione somente os módulos pedidos: Back-end, Admin, Site, Landing Page, Mobile ou Full Stack; consulte os blueprints e `src/front-end/README.md`.
- Para escolhas Front-end, siga as políticas centrais de segurança, testes e DevOps documentadas em `docs/security/frontend-security.md`, `docs/testing/frontend-testing.md` e `docs/devops/frontend-devops.md`.
- Para a Fase 00 — Bootstrap Back-end, consulte `templates/tasks/bootstrap/back-end/`; use `SPEC-000`/`PLAN-000` e aguarde aprovações conforme `AGENTS.md`.
- Não invente que testes, compilação, validação de segurança ou implantação foram executados.
- Nunca reproduza segredos, dados de clientes ou detalhes proprietários.
- Não adicione tecnologias opcionais sem justificar a necessidade.

Arquivos em `.github/agents`, `.github/instructions`, `.github/prompts` e `.github/workflows` são documentais nesta fase; nenhum fluxo de trabalho executável foi criado.
