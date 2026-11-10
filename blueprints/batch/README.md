# Blueprint: Batch

## Objetivo
Executar uma tarefa finita e controlada, manualmente, por scheduler externo ou pipeline operacional.

## Quando utilizar / quando não utilizar
Utilizar para cargas, reconciliações e rotinas com começo/fim e operação definida. Não usar batch para simular worker contínuo nem como endpoint oculto.

## Projetos futuros e dependências
`GFM.Template.Batch` configura o host, opções e saída/exit code; chama Application e Infrastructure. Não contém regra de domínio. Dependências seguem `docs/architecture/dependency-rules.md`.

## Organização de classes
Command/entrypoint validado, caso de uso Application, paginação/chunking, checkpoint explícito e adaptador de persistência. Cada execução deve ter ID e parâmetros auditáveis, sem segredos.

## Segurança e persistência
Identidade de execução de menor privilégio; execução simulada (dry-run) quando útil; limite de escopo e confirmação para operação destrutiva. Transações e checkpoints coerentes; nova tentativa (retry) não duplica efeitos.

## Testes, Docker e CI/CD
Testes unitários para regra/chunk/checkpoint; integração com banco/container descartável; teste de nova tentativa (retry)/retomada; imagem containerizada opcional. CI constrói/testa; execução em ambiente protegido com aprovação humana.

## Observabilidade e diagramas
Registrar início/fim, duração, quantidade e resultado agregado, sem dados pessoais. Draw.io: estados da execução, checkpoints, dependências e fluxo de erro.

## Plano, tarefas e critérios de aceite
Definir volume, janela, concorrência, tempo limite (timeout), retomada, abortagem e reconciliação. Tarefas aprovadas devem cobrir modo de operação, segurança, testes e runbook.

Aceite: execução repetida segura; falhas observáveis e recuperáveis; limites de lote definidos; dados de teste descartáveis; exit code comunica sucesso/falha; runbook aprovado.
