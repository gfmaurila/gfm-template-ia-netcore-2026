# Blueprints de cenário

Cada blueprint é uma referência independente, não uma arquitetura obrigatória. Selecionar somente componentes justificados por requisitos, atributos de qualidade, operação e custo.

## Cenários

- [API REST](api/README.md): API HTTP.
- [Worker](worker/README.md): processamento contínuo.
- [Batch](batch/README.md): execução controlada/agendada.
- [Monólito modular](modular-monolith/README.md): módulos na mesma implantação.
- [Microsserviços](microservices/README.md): serviços com autonomia comprovada.
- [Mensageria](messaging/README.md): integração assíncrona confiável.
- [Integração com IA](ai-integration/README.md): IA opcional e isolada.
- [API + Worker](api-worker/README.md): entrada REST e processamento assíncrono.
- [API + Worker + Batch](api-worker-batch/README.md): API, Worker e rotinas Batch.
- [Admin React](admin-react/README.md): painel administrativo React.
- [Site React](site-react/README.md): aplicação Web interativa React.
- [Landing Page Next.js](landing-page-nextjs/README.md): landing page independente.
- [Mobile React Native](mobile-react-native/README.md): aplicativo React Native/Expo.
- [Full Stack API + Admin](fullstack-api-admin/README.md).
- [Full Stack API + Site](fullstack-api-site/README.md).
- [Full Stack API + Landing Page](fullstack-api-landing-page/README.md).
- [Full Stack API + Admin + Site + Landing Page](fullstack-api-admin-site-landing/README.md).
- [Full Stack API + Web + Mobile](fullstack-api-web-mobile/README.md).

Cada blueprint cobre objetivo, adequação, stack, estrutura, dependências, arquitetura, segurança, testes, Docker, CI/CD, diagramas, bootstrap e aceite. Cenários são independentes; selecionar apenas os módulos aprovados.

O planejamento da fundação Back-end está em [templates/tasks/bootstrap/back-end](../templates/tasks/bootstrap/back-end/README.md); os modelos são independentes dos blueprints e não substituem a seleção do cenário.
