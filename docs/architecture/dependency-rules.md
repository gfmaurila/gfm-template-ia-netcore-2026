# Regras de dependência

## Direção permitida

`Core` não referencia projetos da solução. `Domain -> Core`. `Application -> Domain + Core`. `Infrastructure -> Application + Domain + Core`. Hosts (`API`, `Worker`, `Batch`) fazem composição e podem referenciar Application, Infrastructure e CrossCutting. `CrossCutting`, quando necessário, pode compor registros de Application/Infrastructure na borda.

Projetos de teste referenciam somente a superfície necessária ao tipo de teste. Dependências NuGet e SDKs externos ficam na camada que os usa, normalmente Infrastructure ou host.

## Proibições

- Domain não referencia Infrastructure, Application, hosts, ORM, broker, MediatR ou SDK de fornecedor.
- Application não referencia Infrastructure, CrossCutting, API, Worker ou Batch.
- Infrastructure não referencia hosts nem implementações concretas de outros módulos sem contrato explícito.
- Worker e API não contêm regras de negócio que deveriam estar em Application/Domain.
- CrossCutting não se torna um depósito genérico de utilitários ou dependência transversal.

## Validação futura

Implementar ArchitectureTests para detectar referências proibidas, tipos de infraestrutura vazando em APIs públicas e dependências circulares. As regras serão documentadas antes da implementação e deverão bloquear o Quality Gate quando violadas.
