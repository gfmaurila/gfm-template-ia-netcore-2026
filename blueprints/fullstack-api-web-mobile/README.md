# Blueprint: Full Stack API + Web + Mobile

## 1. Objetivo
Servir jornadas Web e Mobile com back-end/contratos comuns sem assumir interface ou armazenamento compartilhado entre plataformas.

## 2. Quando utilizar
Quando os requisitos aprovados incluem browser e aplicativo móvel. Escolher quais módulos Web (Admin, Site, Landing Page) serão incluídos explicitamente.

## 3. Stack recomendada
API pelo blueprint Back-end; Web pelo blueprint React/Next.js escolhido; Mobile React Native + TypeScript + Expo.

## 4. Estrutura futura
Back-end e cada cliente como módulos separados; `src/front-end/shared/` somente para contratos/utilitários comprovadamente multiplataforma. Releases e signing Mobile separados.

## 5. Dependências
API versionada, autenticação compatível com browser e mobile, gateways/store quando especificados, push/deep-link opcionais com modelo de ameaças.

## 6. Arquitetura
API é autoridade de negócio e autorização. Web e Mobile podem compartilhar contratos neutros, nunca assumir React DOM/React Native equivalentes ou estado/sessão iguais.

## 7. Segurança
Modelo de ameaças de browser e dispositivo; tokens seguros, CSRF conforme cookie, XSS, deep links, permissões e dados offline; API autoriza sempre; segredos/signing fora de bundles e repositório.

## 8. Testes
Web: Vitest/RTL/Playwright se compatíveis. Mobile: Jest/RNTL e E2E por plataforma. API unit/integration/contracts. Testar compatibilidade de contrato e jornadas críticas; DB isolado quando necessário.

## 9. Docker
Docker/Compose para API e dependências temporárias; não substitui emuladores, simuladores ou toolchains nativas. Testes Web podem compartilhar stack local sem fixar ambiente produtivo.

## 10. GitHub Actions
Tarefas por módulo, contrato comum, varreduras e E2E; executores Android/iOS planejados por compatibilidade; segredos protegidos e publicação/distribuição com aprovação.

## 11. Diagramas Draw.io
C4 Context/Container, API→Web/Mobile, fluxos de autenticação, deep link/push opcionais, implantação e fronteiras de confiança.

## 12. Bootstrap
Selecionar módulos Web, autenticação e contrato; planejar API, Web, Mobile, API compatibility, pipeline/signing e tasks independentes com dependências explícitas.

## 13. Critérios de aceite
Clientes independentes; contrato compatível; controles de browser/dispositivo adequados; compilações e testes de plataformas suportadas; autorização server-side; gates/publicação aprovados.
