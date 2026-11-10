# Blueprint: Landing Page Next.js

## 1. Objetivo
Presença pública para apresentar produto/serviço, converter ações e atender requisitos de indexação, com ciclo de publicação independente.

## 2. Quando utilizar
Usar para marketing/conteúdo público quando SEO, renderização, metadata ou desempenho justificarem. Não substituir Site/Admin nem introduzir Next.js sem necessidade.

## 3. Stack recomendada
Next.js + TypeScript; escolher versão/router e estratégia SSR/SSG/ISR conforme conteúdo e requisitos. Confirmar compatibilidade de ferramentas.

## 4. Estrutura futura
`app/` ou router aprovado, layouts, componentes por seção, metadata, assets revisados e integrações server-only isoladas.

## 5. Dependências
CMS/formulário/analytics opcionais; selecionar somente com requisitos e revisão de privacidade. Publicação, domínio e segredos próprios; sem acoplamento obrigatório à API ou outros módulos.

## 6. Arquitetura
Hero, produto, benefícios, funcionalidades, CTA e formulários como seções/componentes. Configurar metadata, Open Graph, canonical, sitemap e política de indexação por rota.

## 7. Segurança
Validar formulários no servidor, limitar abuso, minimizar dados; analytics autorizado; segredos só server-side; XSS, CSP/headers e privacidade conforme linha de base. Conteúdo externo é não confiável.

## 8. Testes
Vitest/RTL compatíveis para componentes e formulários; testar metadata/rendering; Playwright para CTA e submissão; acessibilidade, links e Core Web Vitals conforme metas.

## 9. Docker
Container Web opcional; não requerido para publicação gerenciada quando não agrega reprodutibilidade. Avaliar saída independente/implantação conforme destino sem criar Dockerfile nesta fase.

## 10. GitHub Actions
Lint, verificação de tipos, unit/component, E2E, acessibilidade/performance selecionados, dependency/varredura de segredos e compilação. Publicação independente exige revisão/aprovação e segredos protegidos.

## 11. Diagramas Draw.io
C4 Context/Container, fluxo formulário→API, fronteiras públicas/privadas e implantação/CDN quando relevante.

## 12. Bootstrap
Definir conteúdo/SEO, router/rendering, design, formulários, consentimento/analytics, observabilidade, testes e pipeline em tarefas futuras aprovadas.

## 13. Critérios de aceite
Publicável sem demais módulos; metadata/sitemap corretos; design responsivo e acessível; formulário protegido; analytics aprovado; metas de performance e gates documentados/aprovados.
