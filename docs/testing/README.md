# Política de testes

## Obrigatoriedade por tarefa

Toda tarefa futura que altere código deve avaliar testes unitários, integração e tipos adicionais pertinentes. Testes aplicáveis são executados antes de concluir. Se uma integração não se aplica, registrar justificativa técnica específica; não criar teste artificial.

## Testes unitários

Padrão inicial: xUnit. Usar mocks/fakes/dados de teste (fixtures) conforme isolamento e sem ocultar comportamento. Cobrir cenário positivo, inválido/negativo, limites e falhas relevantes. Exigir asserções que provem resultado ou efeito. Proibidos testes vazios, asserções triviais sem valor e teste que apenas replique implementação.

## Testes de integração e ambiente temporário

Obrigatórios quando alterar persistência, mensageria, APIs, contratos ou integração externa. Usar Testcontainers quando for adequado, com recursos descartáveis. Aplicar esquema/migrations necessários, dados fictícios e limpar recursos também em falha/cancelamento. Ver `integration-database-policy.md`.

É proibido executar DROP, truncar ou limpar recursos de banco compartilhado, dev, homologação ou produção. Toda conexão deve ser validada como temporária antes de qualquer operação destrutiva.

## Testes adicionais

- ArchitectureTests: fronteiras e dependências.
- ContractTests: compatibilidade API/evento.
- EndToEndTests: jornadas críticas e reduzidas.
- Mensageria: entrega, nova tentativa (retry), DLQ, idempotência e ordenação aplicáveis.
- Resiliência: tempo limite (timeout), falha transitória e degradação deliberada.
- Segurança: autorização, validação, mascaramento e casos relevantes do modelo de ameaças.

## Execução e evidências

Executar unitários rápidos, integrações aplicáveis e todos os gates antes do encerramento. Registrar comandos, versão/ferramenta, resultado, relatório e limpeza. Nenhum teste foi criado ou executado nesta fase documental.

[Estratégia de testes Front-end](frontend-testing.md) complementa esta política para React Web, Next.js e React Native/Expo. Verificar compatibilidade das ferramentas com as versões escolhidas em cada projeto.
