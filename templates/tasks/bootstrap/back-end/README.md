# Fase 00 — Bootstrap Back-end

Modelos reutilizáveis de planejamento para fundação de back-end. Não são tarefas de um projeto real, não executam ações e não substituem `templates/tasks/task-template.md` nem o Bootstrap Front-end.

## Uso e gates

1. Criar uma SPEC de projeto a partir do modelo geral; `SPEC-000-fundacao-tecnica.md` é uma extensão documental, não uma SPEC já aprovada.
2. Preencher `PLAN-000-bootstrap.md` após a aprovação da SPEC e das decisões arquiteturais necessárias.
3. Aprovar o PLAN e autorizar explicitamente o escopo de cada tarefa antes de qualquer implementação.
4. Copiar/adaptar somente tarefas aplicáveis, vinculando-as à SPEC/PLAN reais. Não executar os modelos no template.

`TASK-BE-000` auxilia o levantamento e a proposta de stack; a seleção deve ser registrada/aprovada na SPEC antes do PLAN detalhado. A aprovação documental não autoriza código, infraestrutura ou implantação.

## Catálogo e dependências propostas

| Modelo | Dependências reais propostas | Aplicabilidade |
|---|---|---|
| [TASK-BE-000 — Requisitos e stack](TASK-BE-000-requisitos-stack.md) | Solicitação inicial; precede o plano detalhado | Obrigatória |
| [TASK-BE-001 — Estrutura base](TASK-BE-001-estrutura-base.md) | BE-000 | Obrigatória |
| [TASK-BE-002 — Arquitetura e dependências](TASK-BE-002-arquitetura-dependencias.md) | BE-000, BE-001 | Obrigatória |
| [TASK-BE-003 — Configurações e ambientes](TASK-BE-003-configuracoes-ambientes.md) | BE-000, BE-002 | Obrigatória |
| [TASK-BE-004 — Persistência e migrations](TASK-BE-004-persistencia-migrations.md) | BE-002, BE-003; somente se persistência existir | Condicional |
| [TASK-BE-005 — Docker e Compose](TASK-BE-005-docker-compose.md) | BE-001, BE-003; outros serviços conforme cenário | Condicional |
| [TASK-BE-006 — Banco temporário de testes](TASK-BE-006-banco-testes.md) | BE-004 e BE-005; somente com persistência | Condicional |
| [TASK-BE-007 — Testes automatizados](TASK-BE-007-testes-automatizados.md) | BE-001, BE-002 e tasks de integração aplicáveis | Obrigatória |
| [TASK-BE-008 — Segurança](TASK-BE-008-seguranca.md) | BE-000, BE-002, BE-003; revisão transversal | Obrigatória |
| [TASK-BE-009 — GitHub CI](TASK-BE-009-github-ci.md) | BE-007, BE-008; ambientes efêmeros aplicáveis | Obrigatória |
| [TASK-BE-010 — GitHub CD](TASK-BE-010-github-cd.md) | BE-009; implantação solicitado | Condicional |
| [TASK-BE-011 — Observabilidade](TASK-BE-011-observabilidade.md) | BE-000, BE-002, BE-003 | Obrigatória conforme operação |
| [TASK-BE-012 — Diagramas Draw.io](TASK-BE-012-diagramas-drawio.md) | BE-002 e decisões/fluxos definidos | Obrigatória conforme cenário |
| [TASK-BE-013 — Validação do Bootstrap](TASK-BE-013-validacao-bootstrap.md) | Todas as tasks aplicáveis, inclusive BE-014 | Obrigatória |
| [TASK-BE-014 — Mensageria](TASK-BE-014-mensageria.md) | BE-002, BE-003, BE-008; somente se mensageria for requisito | Condicional |

O PLAN poderá paralelizar tarefas independentes após fechar pré-requisitos. BE-014 é opcional; se adotada, integrar seus contratos e testes às tasks de persistência, testes, CI, observabilidade e diagramas aplicáveis. Manter a ordem/dependências reais do projeto no PLAN.

## Outras linguagens

Para Java, Python, PHP ou outra stack aprovada, definir estrutura e ferramentas idiomáticas do ecossistema. Os nomes de projetos e camadas .NET são apenas referência condicional; não impor estrutura .NET às demais linguagens.

## Integração Full Stack opcional

Se uma SPEC selecionar Front-end, definir contratos de API/versionamento, autenticação e autorização, CORS restrito, configuração por ambiente, Docker Compose integrado, testes Web/API e E2E, CI por módulo/contrato e segurança entre fronteiras. Isso não cria dependência de Front-end para projetos Back-end-only. Coordenar com `../front-end/README.md` e os blueprints Full Stack.
