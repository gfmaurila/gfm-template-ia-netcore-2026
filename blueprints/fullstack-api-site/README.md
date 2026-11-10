# Blueprint: Full Stack API + Site

## 1. Objetivo
Entregar API e experiência Web interativa integrada por contratos explícitos.

## 2. Quando utilizar
Quando jornada do produto precisa de browser e API. Usar Landing Page separada apenas se SEO/marketing e publicação independente forem requisitos.

## 3. Stack recomendada
API conforme blueprint Back-end aprovado; Site React + TypeScript + Vite; considerar Next.js por SSR/SEO documentados.

## 4. Estrutura futura
Back-end conforme API blueprint; Web em `src/front-end/web/site/`; fronteiras, projetos e implantação documentados, sem dependência circular.

## 5. Dependências
API contract/versioning, identidade quando necessária, configuração por ambiente; APIs e dados com responsabilidade no servidor.

## 6. Arquitetura
Funcionalidades do Site por capacidade, integração por cliente de API tipado/validado; operações e regras de negócio no back-end.

## 7. Segurança
XSS/CSRF/session review; autorização na API; CORS restrito; validação server-side; CSP/headers e proteção de dados/logs.

## 8. Testes
Site unit/component/accessibility/E2E; API unit/integration/contract; testes de integração usando DB descartável apenas quando persistência envolvida.

## 9. Docker
Compose opcional para Site/API/dependências efêmeras. Não incluir credenciais reais; destruir recursos de teste com identificação isolada.

## 10. GitHub Actions
Gates independentes por módulo mais contrato/E2E integrado; dependency/varreduras de segredos; publicação protegida e artefatos identificados.

## 11. Diagramas Draw.io
C4 Context/Container, browser→API→DB, identidade/confiança e implantação.

## 12. Bootstrap
Aprovar API/Site SPECs; decidir contrato, sessão, origem/implantação; usar tarefas da Fase 00 para Site e tarefas autorizadas para API.

## 13. Critérios de aceite
Jornadas e contratos aprovados; API autoriza; UI responsiva/acessível; integração testada; implantação/configuração não expõem segredos; gates aprovados.
