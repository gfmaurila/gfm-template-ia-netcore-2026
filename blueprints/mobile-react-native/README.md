# Blueprint: Mobile React Native + Expo

## 1. Objetivo
Aplicativo móvel Android/iOS como cliente independente de APIs aprovadas.

## 2. Quando utilizar
Somente quando capacidades/distribuição móvel forem requisitos. Não selecionar para substituir Web sem necessidade de UX ou dispositivo.

## 3. Stack recomendada
React Native + TypeScript + Expo; Expo Router recomendado após verificar compatibilidade do SDK e estratégia de compilação.

## 4. Estrutura futura
Rotas/layouts Expo Router em `app/`; `src/features/<feature>/{screens,components,hooks,services,schemas,types}`, `services/`, `theme/`, `assets/`.

## 5. Dependências
APIs/contratos versionados; permissões de câmera, localização, notificações etc. somente com justificativa; SDKs e libraries revistos por compatibilidade e segurança.

## 6. Arquitetura
Screens/navegação na borda; features e serviços desacoplados de plataforma quando possível; API clients com validação; integrações nativas via adaptadores; dados offline com responsabilidade/expiração.

## 7. Segurança
Armazenamento seguro do token; deep links, backups, logs, screenshots e dados locais no modelo de ameaças; least privilege de permissões; signing protegido; API sempre autoriza.

## 8. Testes
Jest + React Native Testing Library quando compatíveis; testes de navegação, telas, permissões e API; E2E Mobile em simulador/emulador/dispositivo e matriz de plataforma definidos.

## 9. Docker
Docker para serviços backend auxiliares e testes se útil. Docker não substitui Android/iOS SDKs, simuladores, emuladores, signing ou compilação nativo.

## 10. GitHub Actions
Lint/verificação de tipos/testes e varreduras; planejar executores adequados para Android/iOS, segredo de assinatura e distribuição protegida. Sem publicação automático por padrão.

## 11. Diagramas Draw.io
C4 Context/Container, navegação, fluxo de dados/permissões, confiança dispositivo/API e processo de compilação/distribuição.

## 12. Bootstrap
Escolher SDK, roteador, tema, arquitetura de funcionalidades, autenticação/armazenamento seguro, permissões, API, testes, compilações e pipeline por tarefas autorizadas.

## 13. Critérios de aceite
Android/iOS suportados explicitamente; tokens e permissões seguros; navegação/acessibilidade verificadas; API resiliente; testes por plataforma e distribuição documentados.
