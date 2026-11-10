# TASK-BE-006 — Banco de testes descartável

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir ciclo isolado e comprovável para testes de persistência.

## Cenários aplicáveis
Obrigatório quando testes exercitam persistência; se não houver banco, justificar não aplicabilidade.

## Pré-requisitos e dependências
BE-004; BE-005 quando container for usado. Seguir `docs/testing/integration-database-policy.md`.

## Entradas necessárias
Banco descartável, identificador/labels, migrations, dados sintéticos, tempo limite (timeout), limpeza e orphan recovery.

## Escopo autorizado
Especificar salvaguardas; não conectar nem executar comandos de DB/container.

## Atividades futuras
1. Criar DB temporário isolado e validar identidade.
2. Criar estruturas/aplicar migrations e carregar dados fictícios.
3. Executar testes de integração e validar resultados.
4. Limpar estruturas temporárias, destruir DB/container e registrar evidências.
5. Tratar encerramento e limpeza em falha/cancelamento e recursos órfãos após interrupção.

## Entregáveis esperados
Procedimento reproduzível, guardrails contra DB compartilhado/produção e política de limpeza de recursos órfãos.

## Critérios de aceite
DB inteiro temporário e exclusivo; identificação verificada antes de operações destrutivas; encerramento e limpeza sempre ativo; eliminar todas as tabelas via destruição do DB; nenhum alvo compartilhado.

## Testes obrigatórios aplicáveis
Futuramente testar ciclo de setup/migration/data/test/encerramento e limpeza em sucesso e falha; comprovar que alvo não temporário é recusado.

## Segurança
Sem dados reais; conexão de teste dedicada/least privilege; bloquear configuração para ambiente compartilhado/produção.

## Evidências exigidas
Identificador sanitizado, resultado da suíte, confirmação de DB/container/rede/volume destruídos e tratamento de órfãos.

## Riscos
DROP/limpeza no ambiente errado ou recursos órfãos; abortar se qualquer identificação não for inequívoca.

## Critérios de conclusão
Isolamento, recusa de alvos proibidos e limpeza em todos os caminhos comprovados.
