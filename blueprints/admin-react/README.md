# Blueprint: Admin React

## 1. Objetivo
Painel administrativo para usuários autorizados executarem operações internas de produto; não é uma API nem a fonte de regras de negócio autoritativas.

## 2. Quando utilizar
Selecionar para fluxos de trabalho administrativos com navegação, formulários, tabelas, filtros e permissões. Não selecionar para páginas públicas de marketing nem se não houver necessidade administrativa.

## 3. Stack recomendada
React + TypeScript + Vite. Definir router, forms/esquema, data fetching e estado somente após validar requisitos e compatibilidade das versões.

## 4. Estrutura futura
`app/` e providers; `layouts/`; `routes/`; `features/<feature>/{pages,components,hooks,services,schemas,types}`; `services/` para cliente HTTP; `design-system/` para tokens/componentes Admin.

## 5. Dependências
API autenticada e contratos versionados; dependências no cliente revisadas. Não incluir segredos no bundle. Permissões do frontend nunca substituem a autorização da API.

## 6. Arquitetura
Composição/provider separada de feature; componentes focados; validar dados externos em runtime; cliente HTTP centralizado; estado global somente quando justificado; sem acoplamento com Mobile.

## 7. Segurança
Rotas protegidas para UX; enforcement server-side; sessão/token conforme `docs/security/frontend-security.md`; prevenir XSS/CSRF conforme sessão; redigir PII e não logar payloads.

## 8. Testes
Vitest quando compatível, React Testing Library, testes de hooks/forms/API e Playwright para jornadas críticas. Incluir testes de acessibilidade e autorização visual sem confundir com teste de autorização do servidor.

## 9. Docker
Container Web opcional para ambiente de desenvolvimento/implantação. Usar Docker Compose apenas se API/dependências isoladas precisarem de ambiente reproduzível; não criar config nesta fase.

## 10. GitHub Actions
Planejar lint, verificação de tipos, unit/component, acessibilidade selecionada, E2E isolado, dependency/varredura de segredos e compilação. Publicação controlada com aprovação.

## 11. Diagramas Draw.io
Descrever C4 Context/Container, fronteiras Admin/API/IdP e sequência de autenticação ou fluxo administrativo; não incluir dados reais.

## 12. Bootstrap
Executar somente após autorização futura: escolher stack/versões, estruturar app, rotas/layout, tokens, API client, autenticação, erros, testes, observabilidade e pipeline usando `templates/tasks/bootstrap/front-end/`.

## 13. Critérios de aceite
Funcionalidades isoladas; permissões no servidor; formulários/tabelas acessíveis; erros e estados definidos; nenhuma credencial no cliente; gates e evidências aprovados.
