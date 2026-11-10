# Linha de base de segurança

- Armazenar segredos em cofre/segredo manager ou mecanismo seguro de desenvolvimento; não em fonte, JSON versionado, prompt, log ou artefato.
- Usar TLS com validação normal do certificado. Nunca instalar callback que aceite qualquer certificado.
- Exigir autenticação e autorização explícitas por endpoint; qualquer rota anônima precisa de justificativa e aprovação.
- Restringir CORS às origens necessárias. Não combinar origem irrestrita com credenciais.
- Aplicar menor privilégio a identidades, bancos, brokers, pipelines e agentes.
- Validar e limitar entrada; usar queries parametrizadas; evitar erros que revelem stack trace ou detalhes internos.
- Redigir PII e segredos em logs; definir propósito, acesso, retenção e auditoria para dados persistidos.
- Usar apenas dados fictícios ou anonimizados em testes.
- Auditar dependências e segredos em código e artefatos; bloquear credenciais conhecidas e vulnerabilidades segundo política definida.
- Proteger ambientes de implantação, exigir aprovação para produção e preferir federação/OIDC a credenciais duradouras.
- Rever mudanças de autenticação, autorização, criptografia, dados pessoais, mensageria e exposição de rede.

Encontrar segredo exige interromper sua divulgação e orientar rotação/revogação; apagar o valor da cópia local não invalida a credencial nem o histórico.
