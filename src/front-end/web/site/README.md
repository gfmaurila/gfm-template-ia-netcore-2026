# Site Web interativo

## Stack e organização

Padrão inicial: React + TypeScript + Vite, com organização por funcionalidades. Considerar Next.js quando SSR, SEO, geração estática, roteamento integrado ou capacidades específicas forem requisitos demonstrados; registrar a decisão no ADR/plano, sem adicionar framework por tendência.

Estrutura futura a adaptar:

```text
src/
  app/                 # composição e providers
  routes/              # rotas e políticas de navegação
  layouts/             # layouts públicos/privados
  features/<feature>/  # pages, components, hooks, services, schemas, types
  components/          # interface compartilhada do Site
  services/            # clientes e integrações
```

## Comportamento e qualidade

- Separar rotas públicas e privadas; autenticação somente quando necessária.
- Manter páginas/layouts/componentes/hook por feature; evitar componentes globais com responsabilidades de negócio.
- Integrar APIs por clientes tipados, validando dados externos em runtime onde necessário e mantendo erros explícitos.
- Definir gerenciamento de estado pelo escopo; não adotar store global sem justificativa.
- Validar formulários com feedback acessível e sem confiar somente na validação no cliente.
- Projetar responsividade mobile-first; atender navegação por teclado, foco, semântica e contraste conforme critérios de acessibilidade.
- Internacionalização é opcional; escolher quando idiomas, formatos ou requisitos de produto justificarem.

## Segurança e aceite

Prevenir XSS evitando HTML não confiável; CSRF depende do mecanismo de sessão/cookies e deve ser avaliado. Tokens/segredos não podem ser embutidos no bundle. APIs devem autorizar operações no servidor. Cobrir componentes/hooks/formulários, integração API e jornadas E2E relevantes. Aceite inclui responsividade, acessibilidade, erros tratados, lint/verificação de tipos/testes e evidências.

Usar `blueprints/site-react/README.md`. Não criar aplicação nesta fase.
