# Blueprint: Microsserviços

## Objetivo
Separar serviços implantáveis autonomamente quando a autonomia operacional trouxer benefício comprovável.

## Quando utilizar / quando não utilizar
Utilizar quando limites de domínio, escala, isolamento, equipe ou ciclo de publicação exigirem independência real. Não utilizar apenas por popularidade ou para dividir camadas em serviços.

## Projetos futuros e dependências
Cada serviço tem seus próprios hosts e módulos, contratos e propriedade de dados. Compartilhar contratos versionados, não entidades/ORM. Cada serviço segue dependências núcleo→adaptadores; evitar biblioteca compartilhada que acople releases.

## Organização de classes
API/Worker por serviço, casos de uso Application, domínio local, adaptadores Infrastructure. Contratos externos têm compatibilidade/versionamento e política de depreciação.

## Segurança e persistência
Autenticação serviço-a-serviço, autorização por ação, identidade mínima, TLS validado e segredos geridos. Database-per-service como objetivo para autonomia; sem transação distribuída como atalho. Sagas/outbox somente com requisito comprovado.

## Testes, Docker e CI/CD
Testes unitários isolados, ContractTests de consumidor/produtor, IntegrationTests por serviço e E2E limitados a jornadas essenciais. Compilação e implantação independentes; gates, implantação gradual e reversão (rollback) seguros por serviço.

## Observabilidade e diagramas
Tracing distribuído, SLOs por serviço, correlação sem PII, dashboards/alertas e runbooks próprios. Draw.io: C4, dependências, fluxo, confiança, implantação e falhas.

## Plano, tarefas e critérios de aceite
ADR deve registrar problema, custos de rede/observabilidade/on-call, dados e governança. Tarefas incluem contrato, responsabilidade, pipeline e operação.

Aceite: limites claros; implantação sem coordenação desnecessária; contratos testados; dados não compartilhados por acesso direto; resiliência e operação demonstradas; custo/benefício aprovado.
