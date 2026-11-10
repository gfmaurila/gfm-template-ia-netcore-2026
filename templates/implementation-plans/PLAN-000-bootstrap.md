# PLAN-000 — Bootstrap Back-end

> Modelo reutilizável. Não é plano de projeto real nem autorização de execução. Aplicar após aprovação da SPEC de fundação.

## Referências e status
- **SPEC aprovada:** [ID/link]
- **ADR/blueprint:** [...]
- **Status:** Rascunho / Em revisão / Aprovado / Obsoleto
- **Aprovadores/data:** [...]
- **Escopo de execução autorizado:** [tarefas/limites; registrar aprovação separadamente]

## Objetivo e stack
[Resultado, linguagem/framework/versões aprovadas e justificativas; link à SPEC.]

## Sequência, dependências e paralelismo

| Ordem/ID | Resultado | Pré-requisitos reais | Paralelizável com | Gate |
|---|---|---|---|---|
| BE-000 | Requisitos e proposta de stack; aprovar SPEC | Solicitação | Nenhum antes da SPEC | SPEC aprovada |
| BE-001 | Estrutura de módulos adequada à stack | BE-000 | — | Responsabilidades aceitas |
| BE-002 | Arquitetura e limites | BE-000, BE-001 | — | Dependências aprovadas |
| BE-003 | Configuração/ambientes seguros | BE-002 | BE-011, BE-012 após contexto definido | Config validada |
| BE-004 | Persistência/migrations | BE-002, BE-003; se aplicável | BE-008 | Estratégia aprovada |
| BE-005 | Containers de runtime/teste | BE-001, BE-003; se aplicável | BE-008, BE-011 | Ambiente reproduzível |
| BE-006 | Banco temporário seguro | BE-004, BE-005; se persistência | BE-007 preparação | Descarte verificado |
| BE-007 | Suítes automatizadas | BE-001, BE-002, integrações aplicáveis | — | Gates de teste |
| BE-008 | Revisão/controles de segurança | BE-000, BE-002, BE-003 | Tasks sem dependência de implementação | Achados tratados |
| BE-009 | CI | BE-007, BE-008, ambientes aplicáveis | — | Gates em PR |
| BE-010 | CD | BE-009; somente se solicitado | — | Aprovação e reversão (rollback) |
| BE-011 | Observabilidade | Requisitos de operação, BE-002/003 | — | Dados sensíveis excluídos |
| BE-012 | Diagramas editáveis | Arquitetura/contextos definidos | — | Diagramas revisados |
| BE-014 | Mensageria | BE-002/003/008; somente se requisito | Tasks de broker/teste conforme desenho | Falhas/idempotência aceitas |
| BE-013 | Validação final | Todas as tasks aplicáveis, incluindo BE-014 | Nenhuma | Bootstrap aprovado |

O PLAN definitivo deve ordenar as tarefas aplicáveis, registrar dependências verdadeiras e explicar paralelismo. A ordem da tabela é sugestão, não licença para iniciar tarefas.

## Arquitetura e estrutura
[Blueprint, módulos, responsabilidades, contratos e direção das dependências. Para outras linguagens, adaptar ao ecossistema sem copiar nomes .NET.]

## Persistência, testes e ambiente
[Banco/migrations/transações/reversão (rollback) quando aplicáveis; estratégia de testes por stack; banco e dependências temporárias identificados; encerramento e limpeza; identificação de recursos órfãos.]

## Segurança e observabilidade
[AuthN/Autorização, segredos, TLS, validação, logs, métricas/traces/integridade, owners, retenção e risco residual.]

## Docker e GitHub Actions
[Ambiente local/teste; tarefas de compilação, lint, testes, arquitetura, segurança e relatórios; CD controlado, OIDC/aprovação quando pertinente.]

## Riscos e mitigação
[Risco, probabilidade/impacto, mitigação, responsável e condição de bloqueio.]

## Critérios de conclusão
- [ ] Todas as tasks aplicáveis foram autorizadas e aceitas.
- [ ] Compilação/testes/gates pertinentes passaram e evidências foram registradas.
- [ ] Banco/container de teste foi descartado e limpeza comprovada.
- [ ] Segurança/documentação/diagramas foram revisados.
- [ ] Pendências e risco residual estão explícitos; qualquer falha obrigatória mantém Bootstrap pendente.

## Aprovação
[Aprovação do PLAN, da ordem e do escopo de execução. Não autoriza automaticamente implantação.]
