# Blueprint: API REST

## Objetivo
Expor recursos/casos de uso por HTTP com contrato explícito, autenticação e erros previsíveis.

## Quando utilizar / quando não utilizar
Utilizar quando consumidores precisam de requisição/resposta, consulta ou comando síncrono. Não usar API como substituta de processamento assíncrono longo, nem criar microserviço só por existir endpoint.

## Projetos futuros e dependências
`GFM.Template.API` compõe HTTP, Application e Infrastructure. Application depende de Domain/Core; Domain depende somente de Core. API não contém regra de negócio nem acesso direto a banco. CrossCutting é opcional para composição.

## Organização de classes
Endpoints/controllers finos; DTOs e mapeamentos na fronteira; Commands/Queries/Manipuladores por caso de uso; Validators na Application; portas no núcleo e adaptadores em Infrastructure.

## Segurança e persistência
Autenticação e políticas de autorização por rota; validação de entrada; TLS validado; CORS restrito; rate limiting quando requisito; logs sem PII/segredos. Persistência somente via caso de uso/repositório e transação justificada. Retornar Problem Details ou contrato uniforme sem detalhes internos.

## Testes, Docker e CI/CD
Testes unitários para regras/casos de uso; IntegrationTests para HTTP, persistência e autenticação; ContractTests para OpenAPI; E2E apenas para jornadas críticas. API containerizada futuramente; CI executa compilação, testes, análise estática e verificações de segurança; implantação protegida.

## Observabilidade e diagramas
Logs estruturados, correlation/trace IDs, métricas e prontidão (readiness)/liveness proporcionais. Criar C4 Context/Container, sequência de fluxo e fronteiras de confiança em Draw.io.

## Plano, tarefas e critérios de aceite
Plano: especificar consumidor, recursos, autenticação, erros, NFRs e OpenAPI; decidir persistência; implementar em tarefas aprovadas. Tarefas separadas para contrato, casos de uso, adaptador, segurança e testes, com dependências reais.

Aceite: contrato revisado; cada rota protegida conforme política; nenhum segredo/PII em logs; testes relevantes aprovados; status/erros coerentes; OpenAPI e evidências atualizados.
