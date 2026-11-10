# TASK-BE-009 — GitHub CI

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir validações automatizadas de pull requisição/compilação para a stack aprovada.

## Cenários aplicáveis
Todo projeto versionado no GitHub que use CI; adaptar se plataforma aprovada for diferente.

## Pré-requisitos e dependências
BE-007 e BE-008; BE-005/006 para integração com serviços temporários.

## Entradas necessárias
Runtime/SDK, lockfile, comandos de lint/compilação/test, gates, executor constraints, segredo/dependency policy.

## Escopo autorizado
Planejar tarefas, permissões e artefatos; não criar fluxo de trabalho YAML ou executar pipeline.

## Atividades futuras
Documentar checkout/setup/restauração, lint/analisadores, compilação, suites, segredo/verificações de dependências, relatórios e status checks.

## Entregáveis esperados
Matriz de pipeline por evento, tarefas, prerequisites, falha policy, retenção e aprovação.

## Critérios de aceite
Gates obrigatórios bloqueiam merge; testes de integração usam recursos temporários; falha não é mascarada; versões e actions revisadas/fixadas.

## Testes obrigatórios aplicáveis
Validar no futuro cada tarefa em branch/PR de teste autorizado, inclusive falha e encerramento e limpeza; no template somente revisão documental.

## Segurança
Least privilege; segredos protegidos; evitar executar código não confiável em contextos privilegiados; artefatos sem dados sensíveis.

## Evidências exigidas
Resultados futuros de fluxo de trabalho, relatórios sanitizados e proteção de branch/status checks.

## Riscos
Permissões excessivas, cache contaminado, credenciais em fork ou fluxo de trabalho que não bloqueia merge.

## Critérios de conclusão
CI executa e aplica gates definidos; relatório/retenção revisados; sem fluxo de trabalho executável criado nesta fase.
