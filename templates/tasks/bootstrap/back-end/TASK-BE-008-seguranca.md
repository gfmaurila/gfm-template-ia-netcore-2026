# TASK-BE-008 — Segurança

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Planejar controles e revisões de segurança para a superfície e os dados do back-end.

## Cenários aplicáveis
Todo serviço; profundidade conforme dados, exposição, integrações e modelo de ameaças.

## Pré-requisitos e dependências
BE-000, BE-002, BE-003; acompanhar persistência/mensageria se selecionadas.

## Entradas necessárias
Modelo de ameaças, dados/classificação, endpoints, identidades, ambientes, dependências e requisitos regulatórios aprovados.

## Escopo autorizado
Documentar controles e tarefas de verificação; não implementar autenticação/config nem executar varreduras nesta fase.

## Atividades futuras
Definir authentication/authorization, validação, segredos, TLS, CORS restritivo, erros, logs, auditoria, auditoria de dependências e revisão por mudança.

## Entregáveis esperados
Linha de base de segurança do projeto, controles por boundary, revisão de ameaças e evidências previstas.

## Critérios de aceite
Menor privilégio; authn/autorização explícitos; entradas validadas; TLS normal; erros sem detalhes internos; logs sem sensíveis; dependências/segredos verificados.

## Testes obrigatórios aplicáveis
Planejar negativos de autorização/input, varredura de segredos, dependency checks e testes do modelo de ameaças; justificar controles não aplicáveis.

## Segurança
Aplicar `governance/security/security-baseline.md`; nunca armazenar segredos no repositório, desabilitar TLS ou usar dados reais em testes.

## Evidências exigidas
Modelo de ameaças/revisão sanitizada, varreduras/resultados futuros e achados com responsável/mitigação.

## Riscos
Superfície anônima, bypass de permissão, vazamento em logs ou vulnerabilidade de dependência.

## Critérios de conclusão
Achados críticos tratados/bloqueantes; risco residual aceito por responsável competente; evidências registradas.
