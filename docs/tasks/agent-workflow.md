# Processo inicial e fluxo obrigatório dos agentes

Este processo aplica-se a projetos de qualquer linguagem e framework. O GFM.Template é uma base de engenharia e documentação, não uma aplicação executável. Regras específicas de stack aplicam-se somente quando essa stack for selecionada.

## 1. Início do projeto

Antes de propor implementação, identificar:

- Nome e objetivo do projeto.
- Linguagem, framework e versões pretendidas.
- Tipo de aplicação e blueprint adequado: Back-end, Admin, Site, Landing Page, Mobile ou cenário Full Stack.
- Requisitos funcionais e não funcionais.
- Banco de dados, se necessário.
- Integrações externas e mensageria.
- Autenticação e autorização.
- Estratégia de testes.
- Necessidades de Docker e CI/CD.
- Restrições técnicas, operacionais e de segurança.

Esclarecer informações ausentes que alterem decisões arquiteturais. Se não for possível esclarecê-las, registrar pendências, hipóteses e impacto; não inventar requisitos.

Selecionar somente os módulos explicitamente solicitados e aprovados. Admin, Site, Landing Page e Mobile são cenários opcionais, não um pacote obrigatório. Usar `src/front-end/README.md` para selecionar stack e fronteiras.

### Fase 00 — Bootstrap técnico

Para projeto novo, usar os modelos de fundação técnica em `templates/specifications/SPEC-000-fundacao-tecnica.md`, `templates/implementation-plans/PLAN-000-bootstrap.md` e `templates/tasks/bootstrap/`. Aprovar a SPEC, depois o PLAN e, por fim, o escopo das tarefas antes de qualquer implementação. Selecionar somente tarefas aplicáveis; Fase 00 Back-end e Front-end só são coordenadas quando a SPEC seleciona um cenário Full Stack.

## 2. Especificações — `docs/specs/`

Uma funcionalidade deve ter uma SPEC própria ou vínculo explícito a uma SPEC existente. Usar `templates/specifications/specification-template.md`.

Cada SPEC registra:

1. Identificador e título.
2. Objetivo.
3. Contexto e problema.
4. Escopo e exclusões.
5. Requisitos funcionais.
6. Regras de negócio.
7. Requisitos não funcionais.
8. Requisitos de segurança.
9. Dependências e integrações.
10. Critérios de aceite verificáveis.
11. Dúvidas e decisões pendentes.

A SPEC deve registrar status e aprovação. Aprovar requisitos antes do planejamento detalhado da implementação.

## 3. Arquitetura — `docs/architecture/`

Documentar estilo arquitetural, componentes/responsabilidades, módulos/camadas, direção das dependências, persistência, mensageria, segurança, observabilidade e implantação. Justificar decisões e selecionar um blueprint adequado sem ativar componentes opcionais sem necessidade.

Preparar diagramas necessários, preferencialmente editáveis em Draw.io sob `docs/architecture/diagrams/drawio/`; Mermaid pode complementar. Registrar decisões relevantes como ADRs em `docs/architecture/decisions/`.

## 4. Plano — `docs/implementation-plans/`

Somente depois da aprovação da SPEC e das decisões arquiteturais necessárias, criar um plano usando `templates/implementation-plans/implementation-plan-template.md`. O plano registra referências às SPECs, arquitetura e stack, fases e dependências, persistência, testes, Docker, GitHub Actions, riscos/mitigações e critérios de conclusão.

A aprovação do plano não autoriza automaticamente a implementação nem a implantação.

## 5. Tarefas — `docs/tasks/`

Decompor o plano em tarefas pequenas, rastreáveis e verificáveis usando `templates/tasks/task-template.md`. Cada tarefa informa ID/título, SPEC e plano relacionados, objetivo, escopo permitido, dependências reais, arquivos/componentes previstos, agente responsável, critérios de aceite, testes, requisitos de segurança, evidências, status e resultado.

Estados permitidos: **Pendente**, **Pronta**, **Em execução**, **Em validação**, **Bloqueada**, **Falhou** e **Concluída**. Registrar dependências reais; tarefas sem pré-requisito permanecem independentes.

A implementação só começa após autorização explícita do usuário para a tarefa ou conjunto de tarefas. A autorização não amplia escopo nem permite ações externas ou destrutivas não autorizadas.

## 6. Qualidade obrigatória

- Toda tarefa que modificar código executa testes unitários e de integração aplicáveis.
- Para persistência, integração usa banco temporário isolado, cria tabelas automaticamente, executa testes e destrói recursos descartáveis.
- A limpeza deve ocorrer em sucesso e falha; prever identificação e tratamento de recursos órfãos após interrupção abrupta.
- É proibido executar operações destrutivas em bancos compartilhados ou de produção.
- Reproduzir testes localmente com Docker e/ou Testcontainers conforme o cenário.
- GitHub Actions executa as validações exigidas pelo projeto.
- Não concluir tarefa se validações obrigatórias falharem, não forem executadas ou não tiverem evidências.

Aplicar `docs/testing/integration-database-policy.md` e os Quality Gates em `governance/quality-gates/quality-gates.md`.

Para React Web/Next.js e React Native, aplicar também `docs/testing/frontend-testing.md`. As ferramentas citadas são opções documentais: validar compatibilidade com as versões escolhidas antes de adotá-las.

## 7. Fluxo de execução

1. Receber a solicitação.
2. Identificar linguagem e cenário.
3. Levantar requisitos.
4. Criar ou atualizar SPEC.
5. Aprovar requisitos.
6. Definir arquitetura e diagramas.
7. Registrar ADRs necessários.
8. Criar plano de implementação.
9. Dividir o plano em tarefas.
10. Aprovar plano e escopo de execução.
11. Implementar somente as tarefas autorizadas.
12. Executar testes e verificações de segurança.
13. Registrar evidências sanitizadas.
14. Atualizar documentação e status.
15. Encerrar somente tarefas validadas; caso contrário, manter pendente, bloqueada ou falha conforme o resultado.

## 8. Regras para todos os agentes

- Consultar `AGENTS.md` e a governança pertinente.
- Usar os modelos existentes em `templates/` e selecionar stack/blueprint apropriados.
- Preservar requisitos aprovados; não inventar regras de negócio nem alterar componentes fora do escopo.
- Não expor segredos ou dados proprietários.
- Manter rastreabilidade entre SPEC, PLAN e TASK.
- Registrar impedimentos e falhas; não declarar validação que não ocorreu.
- Atualizar documentação e status após alterações aprovadas.

## 9. Prontidão para implementação

O projeto só está pronto para iniciar implementação quando requisitos estiverem definidos, SPECs aprovadas, arquitetura documentada, diagramas necessários preparados, plano aprovado, tarefas organizadas, testes e segurança definidos, estratégia Docker/CI prevista e escopo de execução autorizado. Até então, permanece na fase de documentação e planejamento.

**Princípio:** primeiro especificar; depois arquitetar, planejar e dividir em tarefas; somente então implementar, testar e validar.
