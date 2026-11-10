# Estratégia documental de GitHub Actions

## Fluxos de trabalho planejados

1. Pull requisição: checkout mínimo, setup da versão .NET aprovada, restauração/compilação, verificação de formatação, analisadores, testes unitários, testes de integração com recursos descartáveis, ArchitectureTests/ContractTests, cobertura e auditoria de dependências/segredos.
2. Main/publicação: repetir Quality Gates; empacotar artefato identificado, assinar/provar proveniência se adotado; publicar somente em registry aprovado.
3. Implantação: fluxo de trabalho separado, ambiente protegido, aprovação explícita, permissões mínimas e OIDC quando compatível. A implantação em produção não é automática por padrão.

## Controles

- Fixar actions por referência imutável/commit conforme política de supply chain.
- Definir permissões `GITHUB_TOKEN` mínimas por tarefa.
- Não usar segredos em fork/PR não confiável nem imprimir contexto sensível.
- Evitar `pull_request_target` para checkout/execução de código não confiável.
- Separar compilação de implantação, usar environment aprovações e registrar artefato promovido.
- Aplicar tempo limite (timeout), concurrency e cancelamento seguros.
- Proteger branch com status checks, revisão obrigatória e regras de merge definidas pelo responsável.

## Gates de merge

Compilação, testes aplicáveis, análise estática, arquitetura, segurança e revisão obrigatória falhando bloqueiam merge. A exceção deve ter aprovação, expiração e justificativa.

## Limite da fase

Este documento descreve desenho futuro. Não cria fluxo de trabalho YAML, implantação ou segredo GitHub.
