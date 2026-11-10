# Blueprint: Integração opcional com IA

## Objetivo
Adicionar capacidade de IA somente a um caso de uso com benefício, risco e métrica definidos.

## Quando utilizar / quando não utilizar
Utilizar quando comparação técnica mostrar valor sobre regras ou busca tradicionais. Não usar para decisão determinística simples, nem enviar PII/segredo sem autorização, base legal, minimização e avaliação de risco.

## Projetos futuros e dependências
Application define uma porta/caso de uso neutro; Infrastructure contém adaptador de provedor/SDK. Domain não conhece modelo, prompt, endpoint ou token. Configuração, segredo e seleção de provedor ficam na composição da borda.

## Organização de classes
Serviço de aplicação, requisição/resposta tipados, adaptador de modelo, política de tempo limite (timeout)/nova tentativa (retry)/custo, prompt versionado e validador de saída. Respostas do modelo são dados não confiáveis; validar esquema e regras antes de uso.

## Segurança e persistência
Minimizar/redigir entrada, proteger logs, gerir retenção e consentimento, proteger contra prompt injection e exfiltração. Restringir ferramentas/ações do modelo; nunca permitir ação irreversível sem validação/autorização independente. Guardar versão do modelo/prompt e metadados sem conteúdo sensível.

## Testes, Docker e CI/CD
Testes unitários com fake determinístico; testes de prompt/avaliação com dados de teste (fixtures) sintéticas; testes de segurança; testes de contrato do adaptador. Não chamar provedor externo no CI padrão. Avaliações com conjuntos de dados aprovados e sem dados reais.

## Observabilidade e diagramas
Medir latência, tempo limite (timeout), erro, tokens/custo e taxa de fallback sem registrar prompts/respostas sensíveis. Draw.io: limites de confiança, fluxo de dados e tratamento de fallback.

## Plano, tarefas e critérios de aceite
Registrar problema, linhas de base, limites, avaliação humana, critérios de reversão (rollback) e privacidade. Tarefas aprovadas incluem modelo de ameaças, adaptador, avaliações e sinalizador de funcionalidade se justificada.

Aceite: saída validada; falhas/tempo limite (timeout) explícitos; limite de custo; fallback seguro definido; segredos fora do repositório; nenhum dado real em testes; benefício medido antes de habilitar.
