# Política de dependências arquiteturais

## Matriz

| Projeto | Pode depender de | Não pode depender de |
|---|---|---|
| Core | BCL e pacotes neutros estritamente necessários | Qualquer projeto da solução ou fornecedor de transporte/persistência |
| Domain | Core | Application, Infrastructure, hosts, ORM, broker, MediatR e SDK externo |
| Application | Domain, Core | Infrastructure, CrossCutting e hosts |
| Infrastructure | Application, Domain, Core | API, Worker, Batch e outros hosts |
| CrossCutting | Application/Infrastructure para composição na borda | Ser dependência de Domain ou Application |
| API / Worker / Batch | Application, Core e composição Infrastructure/CrossCutting | Regras de domínio duplicadas ou acesso direto improvisado a fornecedor |

Infrastructure implementa interfaces definidas pelo núcleo; não as define para depois impor dependência externa ao Domain. CrossCutting é opcional e deve limitar-se à composição/configuração compartilhada.

## Exceções

Toda exceção deve ter ADR com motivação, alcance, custo e plano de revisão. Não aceitar referências circulares, service locator em lógica de negócio ou dependência indireta escondida como padrão.

## Gate

ArchitectureTests devem verificar as regras por assembly e namespaces críticos. A violação bloqueia merge; exceções aprovadas devem ser explícitas e testadas.
