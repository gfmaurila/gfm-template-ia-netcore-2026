# Blueprint: Monólito modular

## Objetivo
Manter módulos de domínio isolados em uma única implantação enquanto o contexto não justifica distribuição.

## Quando utilizar / quando não utilizar
Utilizar como padrão inicial para sistema novo com equipe e operação centralizadas. Não usar se módulos exigem isolamento de escala, segurança, disponibilidade ou ciclo de publicação incompatível.

## Projetos futuros e dependências
Hosts podem compartilhar processo; cada módulo tem limites claros em Domain/Application/Infrastructure ou estrutura vertical equivalente. Módulos só acessam outros módulos por contratos publicados. Core contém apenas abstrações realmente genéricas.

## Organização de classes
Funcionalidades por módulo, manipuladores e serviços Application, agregados e políticas Domain, adaptadores internos Infrastructure. Evitar projeto compartilhado de domínio ou tabela acoplada entre módulos sem contrato.

## Segurança e persistência
Separar autorização e responsabilidade dos dados por módulo; menor privilégio. Esquema/responsabilidade e transações explícitos; módulos não devem gravar diretamente nas tabelas de outro módulo.

## Testes, Docker e CI/CD
Testes unitários por módulo; ArchitectureTests verifica ausência de referências ou importações indevidas; testes de integração para composição e persistência. Uma implantação ou container é suficiente; CI inclui todos os módulos.

## Observabilidade e diagramas
Correlacionar operação por módulo e identificar responsabilidade. Draw.io: C4 Container/Component, contextos delimitados e fluxos entre módulos.

## Plano, tarefas e critérios de aceite
Mapear capacidades, responsabilidade e contratos antes de definir módulos. Implementar fronteiras e testes arquiteturais antes de multiplicar projetos.

Aceite: limites testáveis; mudança interna não exige acoplamento de dados/implementação; transações e responsabilidades claras; implantação simples; decisão de manter monólito registrada.
