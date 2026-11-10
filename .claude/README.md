# Claude Code

Leia primeiro `AGENTS.md` e `CLAUDE.md`. Os diretórios abaixo são reservas documentais; arquivos em Markdown não ativam automaticamente comandos, agentes ou skills.

**IDIOMA OFICIAL: PORTUGUÊS BRASILEIRO (pt-BR).** Produza documentação, explicações, relatórios, critérios de aceite e respostas de trabalho em português brasileiro, salvo necessidade técnica ou solicitação explícita do usuário. Preserve nomes e identificadores técnicos.

- `agents/`: perfis futuros, sujeitos a verificação de formato.
- `commands/`: rascunhos de fluxos reutilizáveis.
- `rules/`: índice de regras específicas complementares.
- `skills/`: propostas de capacidades, sem implementação nesta fase.

Não criar hooks que instalem dependências, acessem serviços ou alterem o ambiente sem autorização explícita.

Para projetos futuros, selecionar somente os módulos aprovados: Back-end, Admin, Site, Landing Page, Mobile ou Full Stack. Consultar `src/front-end/README.md`, os blueprints e as políticas compartilhadas de segurança, testes e DevOps, sem duplicar regras neste diretório.

Para Fase 00 Back-end, usar os modelos em `templates/tasks/bootstrap/back-end/` e obedecer às aprovações e dependências registradas em `AGENTS.md` e `PLAN-000`.
