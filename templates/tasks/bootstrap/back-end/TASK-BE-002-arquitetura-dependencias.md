# TASK-BE-002 — Arquitetura e dependências

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir responsabilidades, contratos e direção das dependências sem presumir padrões desnecessários.

## Cenários aplicáveis
Todo back-end; Clean Architecture/Hexagonal, DDD, CQRS, Repository e Unit of Work somente se resolverem requisitos concretos.

## Pré-requisitos e dependências
BE-000 e BE-001; SPEC/PLAN aprovados.

## Entradas necessárias
Domínios/capacidades, casos de uso, frameworks e infraestrutura candidata, atributos de qualidade.

## Escopo autorizado
Decisões, contratos e validação arquitetural futura; não implementar código ou adicionar framework.

## Atividades futuras
Definir fronteiras/inversão de dependência; avaliar Commands/Queries, Domain/Integration Events, Manipuladores, Repository/Unit of Work; especificar ArchitectureTests.

## Entregáveis esperados
Arquitetura, regras permitidas/proibidas, ADRs e critérios/testes arquiteturais.

## Critérios de aceite
Domain não depende de Infrastructure; Application depende de contratos estáveis; Commands/Queries/events/repositories só entram com justificativa; violações podem ser testadas.

## Testes obrigatórios aplicáveis
Revisão do grafo/documentação; planejar testes arquiteturais para a stack. Não requer banco.

## Segurança
Rever fronteiras de confiança, validação, identidade e responsabilidade; contratos não devem expor detalhes sensíveis.

## Evidências exigidas
Diagrama/grafo, ADRs e aprovação do PLAN.

## Riscos
Abstrações genéricas sem uso, acoplamento de domínio a fornecedores ou eventos sem necessidade.

## Critérios de conclusão
Regras de dependência e justificativas aprovadas; sem isso, tarefas de estrutura permanecem bloqueadas.
