# Blueprint: Site React

## 1. Objetivo
Aplicação Web interativa orientada a jornadas de usuário, independente de uma landing page ou painel administrativo.

## 2. Quando utilizar
Usar para experiência Web autenticada ou pública com interatividade. Não escolher automaticamente quando conteúdo principalmente estático/SEO justificar Next.js.

## 3. Stack recomendada
React + TypeScript + Vite como padrão inicial. Next.js pode ser selecionado quando SSR, SEO, geração estática ou recurso específico for requisito documentado.

## 4. Estrutura futura
`app/` (providers/composição), `routes/`, `layouts/`, `features/<feature>/{pages,components,hooks,services,schemas,types}`, `components/` e `services/`.

## 5. Dependências
APIs e contratos definidos por SPEC. Escolher router, state/data layer e validação em runtime após avaliar compatibilidade; sem estado global ou biblioteca visual obrigatória.

## 6. Arquitetura
Funcionalidades por capacidade; rotas públicas/privadas; layouts compartilhados com fronteiras claras; integração por cliente de API. Regras autoritativas e persistência ficam no servidor.

## 7. Segurança
XSS, CSRF conforme mecanismo de sessão, tokens, validação, CSP/headers do host, privacidade e registro de logs segundo `docs/security/frontend-security.md`.

## 8. Testes
Vitest/React Testing Library se compatíveis; testes de componentes, hooks, formulários e API; Playwright para jornadas críticas; acessibilidade automatizada e revisão manual pertinente.

## 9. Docker
Docker para Web e Compose opcional com API/dependências temporárias. Unit/visual tests não exigem banco; integrações com banco seguem a política de isolamento.

## 10. GitHub Actions
Análise estática (lint), verificação de tipos, testes, acessibilidade selecionada, E2E efêmero, varreduras e compilação; implantação protegida e manual por padrão.

## 11. Diagramas Draw.io
C4 Context/Container, fluxo browser→API, sequência de login quando aplicável e implantação/cache quando necessário.

## 12. Bootstrap
Planejar stack, app/routes/layouts, design tokens, API client, autenticação opcional, erros, testes/acessibilidade, observabilidade e CI por tarefas aprovadas.

## 13. Critérios de aceite
Rotas e estados cobertos; layouts responsivos e acessíveis; dados externos validados; erros seguros; versão/stack justificada; gates aprovados.
