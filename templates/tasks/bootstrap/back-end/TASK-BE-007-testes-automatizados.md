# TASK-BE-007 — Testes automatizados

- **Status:** Pendente
- **SPEC:** `SPEC-000-fundacao-tecnica.md`
- **PLAN:** `PLAN-000-bootstrap.md`

## Objetivo
Planejar testes relevantes e comandos/relatórios por stack aprovada.

## Cenários aplicáveis
Todo back-end; níveis e ferramentas proporcionais ao tipo de serviço.

## Pré-requisitos e dependências
BE-001 e BE-002; BE-004/006 quando persistência.

## Entradas necessárias
Casos de uso, riscos, stack/versões, dependências externas e critérios de cobertura.

## Escopo autorizado
Definir estratégia e evidência; não instalar ferramentas nem criar testes executáveis nesta etapa.

## Atividades futuras
Planejar unit, integration, architecture, contract, E2E e testes de segurança pertinentes, negativos/exceções e relatórios.

## Entregáveis esperados
Matriz de testes, comandos futuros, dados de teste (fixtures), isolamento e quality thresholds justificados.

## Critérios de aceite
Asserções comportamentais; positivos/negativos/falhas; nenhum teste vazio; não inventar cobertura artificial; compatibilidade de ferramenta confirmada para versão escolhida.

## Testes obrigatórios aplicáveis
.NET: xUnit e Testcontainers; Java: JUnit 5 e Testcontainers; Python: pytest e testcontainers-python; PHP: PHPUnit ou Pest com integração isolada. Confirmar versões/compatibilidade no projeto real.

## Segurança
Dados sintéticos; segredos ausentes; autorização, validação, dependências e resiliência testados conforme risco.

## Evidências exigidas
Resultados/comandos/versões/relatórios sanitizados e limpeza de recursos de integração.

## Riscos
Mocks que ocultam integração, assertions vazias ou ferramentas incompatíveis.

## Critérios de conclusão
Todos os testes obrigatórios aplicáveis passam e têm evidências; falha/ausência mantém tarefa pendente.
