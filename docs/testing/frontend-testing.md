# Estratégia de testes Front-end

Selecionar ferramentas compatíveis com as versões efetivamente aprovadas. Registrar versão, configuração e limitações no plano; não assumir compatibilidade somente pelo nome da ferramenta.

## React Web e Next.js

- **Vitest:** testes unitários/componentes quando compatível com bundler, framework e configuração selecionados.
- **React Testing Library:** testar comportamento observável e acessibilidade de componentes, não detalhes internos.
- **Hooks e formulários:** cobrir estados, validação, submissão, erros, interação por teclado e cancelamento quando aplicável.
- **APIs:** usar respostas sintéticas/dublês controlados; testar loading, tempo limite (timeout), erro, validação de carga útil (payload) e autorização na interface.
- **Playwright:** E2E para jornadas críticas e smoke em ambiente efêmero; isolar usuários/dados e evitar serviços reais.
- **Next.js:** testar rotas, metadata, rendering/data boundary e componentes server/client conforme a arquitetura/versão selecionada.
- **Acessibilidade:** combinar assertions automatizadas com verificação manual/leitor de tela para jornadas relevantes; automação não comprova conformidade total.

## React Native + Expo

- **Jest** e **React Native Testing Library** para comportamento de componentes e telas, após verificar compatibilidade Expo/Jest do SDK selecionado.
- Testar navegação/Expo Router, permissões, armazenamento seguro por adaptador falso, estado offline e integração API sem segredo real.
- Definir E2E Mobile e cobertura de dispositivos/emuladores por plataforma; documentar limites de execução em CI.
- Nunca exigir banco real para testes unitários/visuais sem persistência. Integrações que usem banco devem obedecer `integration-database-policy.md`.

## Gates por mudança

Aplicar conforme o escopo: formatter/lint, verificação de tipos, testes unitários, testes de integração, E2E, acessibilidade, análise de dependências/segredos e compilação de produção. Nenhum gate aplicável pode ser omitido sem justificativa aprovada; falha ou ausência de evidência bloqueia conclusão conforme `governance/quality-gates/quality-gates.md`.
