# Fase 00 — Bootstrap Front-end

Extensão documental para a Fase 00. O Bootstrap Front-end e o [Bootstrap Back-end](../back-end/README.md) são conjuntos opcionais e independentes, coordenados somente em projetos Full Stack. Os modelos gerais em `../../README.md` e `../../task-template.md` permanecem válidos; esta pasta contém somente tarefas específicas de Front-end.

Todos os arquivos são modelos Markdown. Não executar as tarefas nem gerar código/configuração sem SPEC, plano aprovado e autorização explícita de escopo.

## Sequência proposta

| Tarefa | Pré-requisito(s) real(is) |
|---|---|
| [FE-00-01 — Selecionar stack](FE-00-01-stack-selection.md) | SPEC aprovada |
| [FE-00-02 — Definir estrutura do módulo](FE-00-02-module-structure.md) | FE-00-01 |
| [FE-00-03 — Definir configuração TypeScript](FE-00-03-typescript-configuration.md) | FE-00-02 |
| [FE-00-04 — Planejar roteamento](FE-00-04-routing.md) | FE-00-02 |
| [FE-00-05 — Planejar Design System](FE-00-05-design-system.md) | FE-00-02 |
| [FE-00-06 — Definir integração com APIs](FE-00-06-api-integration.md) | SPEC/contrato API aprovados; FE-00-02 |
| [FE-00-07 — Definir autenticação e segurança](FE-00-07-auth-security.md) | Modelo de ameaças e contrato de identidade; FE-00-06 quando integrado à API |
| [FE-00-08 — Definir tratamento de erros](FE-00-08-error-handling.md) | FE-00-02 e FE-00-06 |
| [FE-00-09 — Planejar testes automatizados](FE-00-09-automated-tests.md) | Stack e estrutura definidas |
| [FE-00-10 — Avaliar Docker](FE-00-10-docker.md) | Necessidade/ambiente decididos |
| [FE-00-11 — Planejar GitHub Actions](FE-00-11-github-actions.md) | Stack, testes e gates definidos |
| [FE-00-12 — Planejar observabilidade](FE-00-12-observability.md) | Requisitos de operação definidos |
| [FE-00-13 — Planejar diagramas Draw.io](FE-00-13-drawio-diagrams.md) | Arquitetura/contexto definidos |
| [FE-00-14 — Validar bootstrap](FE-00-14-final-validation.md) | Demais tarefas aplicáveis concluídas |

O agente deve copiar o modelo geral de tarefa, completar dependências/escopo para o projeto real e omitir tarefas não aplicáveis com justificativa. Essa lista não autoriza execução e não obriga a adoção de todos os módulos.
