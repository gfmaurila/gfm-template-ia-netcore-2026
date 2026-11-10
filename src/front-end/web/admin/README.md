# Admin Web

## Stack e organização

Stack preferencial: React + TypeScript + Vite. Organizar por funcionalidades e manter fronteiras entre apresentação, estado, contratos e integração. Exemplo de estrutura futura, a adaptar:

```text
src/
  app/                 # bootstrap, providers e composição
  layouts/             # shell e layout administrativo
  routes/              # rotas e guards
  features/<feature>/  # pages, components, hooks, services, schemas, types
  components/          # componentes visuais realmente compartilhados no Admin
  services/            # cliente HTTP e integração transversal
  design-system/       # tokens e componentes de interface
```

## Responsabilidades e segurança

- **App/providers:** inicialização e providers explícitos; evitar estado global incidental.
- **Layout/rotas:** navegação, rotas protegidas e carregamento; guard de rota é UX, não controle de segurança do servidor.
- **Funcionalidades/páginas/componentes/hooks:** interface e estado de apresentação; regras de negócio autoritativas permanecem no back-end.
- **Services/cliente HTTP:** tempo limite (timeout), correlation, serialização e tratamento consistente; não incluir segredos nem tokens em logs.
- **Esquemas/types:** validar dados não confiáveis em fronteiras; tipos TypeScript não substituem validação runtime.
- **Autenticação/autorização:** usar fluxo aprovado; separar identidade de permissão. Controlar permissões tanto na interface quanto na API.
- **Formulários/tabelas/filtros:** validação acessível, estados vazio/loading/erro, paginação segura e filtros sem expor dados.
- **Design System:** tokens e componentes consistentes; evitar dependência com React Native sem compatibilidade demonstrada.
- **Observabilidade:** erros e métricas sem PII, tokens, conteúdo de formulários ou payloads sensíveis.

## Qualidade e aceite

Testar componentes, hooks, formulários, autorização de interface e integração HTTP com dados de teste (fixtures) sintéticos. Aplicar acessibilidade, responsividade, análise estática (lint), verificação de tipos, testes e análise de dependências definidos no plano. Critérios: rotas e permissões coerentes; erros sem detalhes internos; nenhuma credencial no cliente; estados acessíveis; testes e evidências aprovados.

Usar o blueprint `blueprints/admin-react/README.md`. Não implementar componentes nem configurar dependências nesta fase.
