# Quality Gates obrigatórios

## Antes de concluir uma tarefa que altera código

- [ ] Escopo e critérios de aceite atendidos.
- [ ] Arquitetura e dependências respeitam `governance/architecture/dependency-policy.md`.
- [ ] Compilação da solução aprovado.
- [ ] Testes unitários relevantes aprovados e com asserções comportamentais.
- [ ] Testes de integração aplicáveis aprovados com recursos descartáveis.
- [ ] Banco/container de teste e artefatos temporários removidos.
- [ ] Testes de arquitetura, contrato, E2E, mensageria ou segurança aplicáveis aprovados.
- [ ] Formatter, analisadores e análise estática aprovados.
- [ ] Verificação de segredos e dependências executada.
- [ ] Autenticação, autorização, TLS, registro de logs e dados sensíveis revisados.
- [ ] Documentação e diagramas atualizados.
- [ ] Evidências registradas na tarefa.

## Falhas e impedimentos

Falha de gate bloqueia conclusão e merge. Se uma validação não puder ser executada, registrar motivo, impacto e próximo passo; manter a tarefa pendente. Não trocar validação obrigatória por teste artificial ou sucesso presumido.

## Implantação

Implantação em ambiente protegido exige aprovação explícita e evidência da pipeline. Produção não é publicada automaticamente por padrão.
