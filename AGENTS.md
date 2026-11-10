# Instruções compartilhadas para agentes

Estas regras são a fonte central de orientação para GitHub Copilot, OpenAI Codex, Claude Code e OpenCode. Instruções específicas de cada ferramenta devem apontar para este arquivo, sem criar políticas contraditórias.

## Idioma oficial

**IDIOMA OFICIAL: PORTUGUÊS BRASILEIRO (pt-BR).**

Todo agente deve produzir documentação, explicações, relatórios, critérios de aceite e respostas de trabalho em português brasileiro. Exceções são permitidas quando houver necessidade técnica ou solicitação explícita do usuário. Preserve nomes de tecnologias, classes, namespaces, comandos, caminhos e identificadores técnicos.

## Escopo e segurança

- Trabalhe somente no repositório solicitado e respeite os limites declarados pelo usuário.
- Não copie código, dados, contratos, identificadores, credenciais ou regras proprietárias de outros projetos.
- Nunca exponha segredos em código, documentação, logs, testes, prompts ou respostas. Se encontrar material suspeito, não o reproduza; pare alterações relacionadas a ele e comunique o risco.
- Não acesse serviços externos nem execute comandos destrutivos sem autorização explícita e necessária.
- Nunca desabilite validação TLS, autenticação ou controles de autorização como atalho.
- Não use dados reais ou identificáveis em exemplos e testes.

## Fluxo obrigatório de trabalho

Seguir o processo detalhado em `docs/tasks/agent-workflow.md` para qualquer linguagem. Em resumo: levantar requisitos, criar e obter aprovação da SPEC, documentar arquitetura/diagramas/ADRs, produzir e obter aprovação do plano, decompor em tarefas e aguardar autorização explícita de execução.

Uma aprovação de documentação não autoriza implementação de código, infraestrutura ou implantação. Uma tarefa não autorizada permanece pendente. Não avançar para planejamento detalhado antes da aprovação dos requisitos nem implementar antes da autorização explícita do escopo da tarefa.

Para projeto novo, reconhecer a Fase 00 Back-end e usar os modelos de `templates/tasks/bootstrap/back-end/`, com `SPEC-000` e `PLAN-000` indicados nos índices. Coordenar com Front-end apenas quando o escopo aprovado for Full Stack; executar somente tarefas autorizadas e aplicáveis.

## Arquitetura e código futuro

- Em projetos .NET, seguir `governance/architecture/dependency-policy.md`: Core não depende de aplicação/infraestrutura/fornecedores; Domain depende somente de Core; Application depende de Domain/Core; Infrastructure implementa portas; Application não depende de CrossCutting/Infrastructure.
- Para outras linguagens/stacks, definir dependências e limites na arquitetura aprovada, sem presumir a estrutura .NET.
- Preferir abstrações necessárias ao caso de uso; não adicionar CQRS, MediatR, repositório genérico, microsserviço ou eventos por tendência.
- Não suprimir exceções críticas nem retornar sucesso como fallback silencioso.
- Selecionar somente os módulos solicitados e aprovados: Back-end, Admin, Site, Landing Page, Mobile ou combinações Full Stack.
- Para Front-end, seguir `src/front-end/README.md` e os padrões de segurança, testes e DevOps em `docs/security/frontend-security.md`, `docs/testing/frontend-testing.md` e `docs/devops/frontend-devops.md`.
- Stack preferencial: Admin/Site em React + TypeScript + Vite; Landing Page em Next.js + TypeScript; Mobile em React Native + TypeScript + Expo. Validar versões e compatibilidade ao planejar.
- Não presumir compartilhamento entre React DOM e React Native; evitar dependências circulares entre módulos.

## Testes futuros

Qualquer tarefa que altere código deve avaliar testes unitários, integração e demais tipos pertinentes. Testes devem ter asserções relevantes, cobrir cenários positivos e negativos e não podem ser vazios. Testes de integração usam exclusivamente recursos descartáveis e protegidos conforme `docs/testing/integration-database-policy.md`.

Antes de concluir, executar as validações aplicáveis, registrar comandos/resultados e confirmar limpeza de banco/container temporário. Nunca executar `DROP` em banco compartilhado, de desenvolvimento ou produção.

## Evidências e resposta

- Distinguir fato confirmado, inferência e item não verificado.
- Referenciar caminhos, classes e resultados sem incluir dados sensíveis.
- Informar validações não executadas, falhas e bloqueios sem declarar conclusão prematura.
- Atualizar tarefas, plano e documentação afetados.

## Conteúdo atual

Esta pasta está em fase documental. Não criar código, projetos, scripts executáveis, Dockerfiles, arquivos Compose executáveis ou pipelines até autorização explícita para uma fase posterior.
