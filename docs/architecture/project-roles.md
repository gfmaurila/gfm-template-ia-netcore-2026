# Projetos-alvo e responsabilidades

Os nomes abaixo são uma proposta documental para soluções futuras `GFM.Template.*`. Não são projetos já criados.

| Projeto | Responsabilidade e limite |
|---|---|
| `GFM.Template.Core` | Primitivas e abstrações genéricas sem dependência de aplicação, infraestrutura ou fornecedor: Result/Error, contratos genéricos de eventos, paginação e metadados comuns. |
| `GFM.Template.Domain` | Entidades, aggregates, value objects, domain events, enums, exceções de domínio, contratos de repositório e serviços de domínio. Depende somente de Core. |
| `GFM.Template.Application` | Casos de uso por feature: Commands, Queries, Manipuladores, DTOs, Validators, Mappings, Behaviors e serviços de aplicação. Depende de Domain/Core, nunca de Infrastructure/CrossCutting. |
| `GFM.Template.Infrastructure` | Implementações de persistência, repositórios, mensageria, clientes externos, segurança e observabilidade. Implementa portas definidas pelo núcleo. |
| `GFM.Template.CrossCutting` | Composição e configuração compartilhadas, sem lógica de negócio. Pode conectar Application e Infrastructure na borda; nunca deve ser dependência de Application ou Domain. Se não reduzir duplicação real, omitir. |
| `GFM.Template.API` | Host REST, autenticação/autorização, serialização, HTTP, integridade endpoints e composição da API. |
| `GFM.Template.Worker` | Host de processamento contínuo, consumo e agendamento. Chama casos de uso; não duplica o transporte implementado em Infrastructure. |
| `GFM.Template.Batch` | Host para tarefas controladas, execução operacional e rotinas agendadas. Reutiliza Application e Infrastructure. |

### Projetos de teste

- `GFM.Template.UnitTests`: testes isolados de Domain e Application.
- `GFM.Template.IntegrationTests`: integração com Infrastructure e dependências temporárias.
- `GFM.Template.ArchitectureTests`: verifica regras de dependência e convenções.
- `GFM.Template.ContractTests`: compatibilidade de contratos HTTP e de mensagens.
- `GFM.Template.EndToEndTests`: fluxos críticos com hosts e serviços de teste descartáveis.

Adicionar cada projeto somente quando houver comportamento que justifique sua existência. Um teste não deve existir apenas para satisfazer a estrutura.
