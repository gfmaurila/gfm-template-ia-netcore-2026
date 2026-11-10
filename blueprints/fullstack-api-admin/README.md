# Blueprint: Full Stack API + Admin

## 1. Objetivo
Combinar API de domínio com console administrativo autenticado.

## 2. Quando utilizar
Quando operadores precisam gerenciar o domínio via Web. Admin é opcional e não substitui API pública nem autorização server-side.

## 3. Stack recomendada
Back-end conforme blueprint API selecionado (GFM .NET por padrão); Admin React + TypeScript + Vite.

## 4. Estrutura futura
Hosts/API e camadas conforme arquitetura back-end aprovada; `src/front-end/web/admin/` conforme blueprint Admin. Implantações podem ser independentes.

## 5. Dependências
Contrato API versionado, OIDC/IdP ou autenticação aprovada, configuração de origem/CORS estrita; cliente gerado somente com processo compatível validado.

## 6. Arquitetura
Admin chama endpoints de API; regras e autorização no servidor; features de interface por domínio/caso de uso; cliente HTTP e erros coerentes.

## 7. Segurança
Modelo de ameaças browser/API; sessão/token seguro; CSRF quando aplicável; RBAC/permissions enforced na API; logs redigidos; sem segredo no bundle.

## 8. Testes
Unit/component e forms Admin; API unit/integration/contract; testes de autenticação/authorization; E2E limitado à jornada Admin+API; banco temporário só para persistência.

## 9. Docker
Compose pode executar Admin/API/DB temporário para integração. Isolar redes, segredos e volumes; teste visual não exige DB.

## 10. GitHub Actions
Gates front/back separados e contratos compartilhados; compilação/test/varredura; implantação Admin/API coordenado por compatibilidade e aprovação explícita.

## 11. Diagramas Draw.io
C4 Context/Container, sequência Admin→API→persistência/IdP e fronteiras de confiança.

## 12. Bootstrap
Definir SPEC dos fluxos de trabalho, API contract, autorização, implantação boundaries; planejar back-end e tarefas da Fase 00 Front-end sem gerar código nesta fase.

## 13. Critérios de aceite
Contrato compatível; API valida cada operação; Admin acessível/responsivo; erros seguros; integrações isoladas; gates e implantação gradual aprovados.
