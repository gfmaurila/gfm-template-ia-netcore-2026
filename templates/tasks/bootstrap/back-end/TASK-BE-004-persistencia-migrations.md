# TASK-BE-004 — Persistência e migrations

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir se persistência é necessária e, quando sim, seu responsabilidade, esquema e ciclo de evolução.

## Cenários aplicáveis
Somente serviços que persistem dados; caso contrário marcar não aplicável com justificativa na SPEC/PLAN.

## Pré-requisitos e dependências
BE-002 e BE-003; banco e requisitos de dados aprovados.

## Entradas necessárias
Banco/versão, entidades/retenção, volume/consistência, responsabilidade, concorrência, recovery/reversão (rollback).

## Escopo autorizado
Documentar escolha e estratégia; não acessar banco, rodar migration nem gerar SQL/código executável.

## Atividades futuras
Definir entidades/mapeamentos, repositórios se justificados, transações, integridade, esquema/versionamento e reversão (rollback) compatível com dados.

## Entregáveis esperados
ADR de persistência, esquema responsabilidade, plano de migrations/reversão (rollback) e casos de teste.

## Critérios de aceite
Stack aprovada; integridade e concorrência cobertas; migrations revisáveis; reversão (rollback) seguro definido; sem DB compartilhado nos testes destrutivos.

## Testes obrigatórios aplicáveis
Testes de integração em banco temporário para mapping, constraints e transações; cobertura unitária de regras fora do DB.

## Segurança
Least privilege; dados minimizados/classificados; queries seguras; segredos em vault; backups/retenção definidos.

## Evidências exigidas
ADR, plano de migration reversível/expand-contract quando preciso, evidências de teste e limpeza futuros.

## Riscos
Perda/alteração incompatível, locking ou acesso direto entre módulos; documentar mitigação/reversão (rollback).

## Critérios de conclusão
Estratégia aprovada ou não aplicabilidade justificada; nenhuma migration executada nesta etapa.
