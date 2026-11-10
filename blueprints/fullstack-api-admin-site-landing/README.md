# Blueprint: Full Stack API + Admin + Site + Landing Page

## 1. Objetivo
Solução com API, interface administrativa, aplicação Web de produto e presença pública; módulos continuam selecionáveis e publicáveis conforme necessidade.

## 2. Quando utilizar
Somente quando os quatro módulos tiverem requisitos distintos e responsabilidade claros. Não implementar todos por padrão nem compartilhar publicação sem justificativa.

## 3. Stack recomendada
API pelo blueprint Back-end; Admin e Site React + TypeScript + Vite; Landing Page Next.js + TypeScript.

## 4. Estrutura futura
Separar `src/back-end/`, `src/front-end/web/admin/`, `site/` e `landing-page/`; considerar pipelines e implantações independentes por módulo. Usar `shared` somente para contratos neutros.

## 5. Dependências
SPEC/contratos por consumidor, autenticação/IdP, domínios/origens/CORS; versionamento compatível e responsabilidade documentado.

## 6. Arquitetura
API centraliza regras/autorização; Admin foca operação, Site foca jornadas, Landing Page foca conteúdo/conversão; não compartilhar navegação/estado entre módulos sem justificativa.

## 7. Segurança
Análise separada de browser/admin público, session/CSRF, API authorization, CSP, formulários, privacidade/analytics e segredos por ambiente.

## 8. Testes
Suites específicas por módulo; testes de contrato de API; E2E por jornada crítica; acessibilidade para Web; persistência via DB descartável; evitar suíte gigante acoplada.

## 9. Docker
Compose Full Stack opcional para integração, serviços isolados e temporários; não é requisito para compilação/test unitário. Não compartilhar volume de DB.

## 10. GitHub Actions
CI por projeto e gates integrados por contrato; implantações independentes ou coordenados mediante aprovação e compatibilidade.

## 11. Diagramas Draw.io
C4 Context/Container; sequências Admin/API, Site/API, CTA/API; implantação por módulo e limites de confiança.

## 12. Bootstrap
Priorizar SPECs por audiência, definir módulo inicial, contratos/domínios; executar somente tarefas aprovadas de bootstrap por módulo, evitando scaffold não solicitado.

## 13. Critérios de aceite
Cada módulo tem finalidade/responsável; API autoriza; contratos compatíveis; publicação independente quando exigida; testes, segurança e gates de cada módulo aprovados.
