# TASK-BE-001 — Estrutura base

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Definir estrutura documental dos módulos/hosts necessários à stack aprovada.

## Cenários aplicáveis
Todos os back-ends; API/Application/Domain/Core/Infrastructure/CrossCutting, Worker e Batch somente conforme requisitos para .NET. Java, Python, PHP e outras stacks seguem padrões idiomáticos.

## Pré-requisitos e dependências
SPEC/stack aprovada; TASK-BE-000. Depende de decisão arquitetural quando necessário.

## Entradas necessárias
Linguagem/framework/versões, blueprint, limites funcionais, implantação e requirements operacionais.

## Escopo autorizado
Planejar diretórios/projetos e responsabilidades; não gerar soluções, projetos ou código.

## Atividades futuras
Registrar mapa da solução, módulos obrigatórios/opcionais, composition roots e estratégia de naming por stack.

## Entregáveis esperados
Estrutura proposta, owners e critérios para adicionar/remover módulo.

## Critérios de aceite
Cada módulo tem responsabilidade e fronteira; opções não justificadas são excluídas; nenhuma estrutura .NET é imposta a outra linguagem.

## Testes obrigatórios aplicáveis
Documentação: verificar coerência com blueprint. Futuramente, ArchitectureTests aplicáveis validam referências e fronteiras.

## Segurança
Separar superfície pública, segredos, dados e hosts; não introduzir acesso direto indevido entre módulos.

## Evidências exigidas
Mapa/revisão de arquitetura e aprovação no PLAN.

## Riscos
Modularização excessiva, dependências circulares ou nomenclatura não idiomática; registrar tradeoffs.

## Critérios de conclusão
Estrutura e composição aprovadas; se fronteiras não forem verificáveis, manter Bloqueada.
