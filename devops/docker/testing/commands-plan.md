# Comandos planejados para ambiente de teste

Este documento é uma proposta, não um script. Os comandos abaixo só deverão ser habilitados depois de criar e revisar os artefatos executáveis e o isolamento descrito em `docs/testing/integration-database-policy.md`.

| Ação futura | Intenção |
|---|---|
| Inicializar ambiente | Provisionar broker/banco temporário com ID único e confirmar labels de teste. |
| Testes unitários | Executar testes sem dependência externa. |
| Testes de integração | Executar suite apontando somente para containers temporários validados. |
| Todos os testes | Executar gates na ordem definida pela pipeline. |
| Relatórios | Gerar cobertura/relatório de testes sem dados confidenciais. |
| Encerrar | Parar somente o projeto Compose identificado para esta execução. |
| Remover temporários | Descartar container, rede, volume e banco com labels/ID da execução; verificar resultado. |

Em implementação futura, documentar comandos concretos e seus pré-requisitos. Nunca adicionar opção de remoção de volumes compartilhados nem assumir contexto Docker atual.
