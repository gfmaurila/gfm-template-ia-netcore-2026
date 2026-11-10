# Segurança de integrações com IA

- Classificar dados antes de enviar a modelo/provedor; aplicar minimização, redação ou não envio para PII, segredo, credencial, propriedade intelectual e dados regulados sem aprovação.
- Considerar prompts, documentos recuperados e saída do modelo como entrada não confiável.
- Não conceder ao modelo acesso direto a credenciais, shell, banco ou ferramentas de escrita sem política explícita e autorização humana.
- Validar esquema, conteúdo, limites e autorização da resposta antes de usar em operação.
- Proteger contra prompt injection, exfiltração, conteúdo adversarial e chamadas de ferramenta fora de escopo.
- Isolar tenant/usuário; evitar mistura entre sessões e conteúdo indexado sem autorização.
- Não registrar prompt/resposta sensível; registrar metadados mínimos para auditoria.
- Versionar prompts e avaliações; testar regressão com dados sintéticos.
- Definir tempo limite (timeout), nova tentativa (retry) limitado, fallback seguro, teto de custo e kill switch/sinalizador de funcionalidade quando justificado.
- Verificar retenção, região, treinamento sobre dados, suboperadores e termos do provedor antes de produção.

Uso de IA não substitui autenticação, autorização, regra determinística, revisão humana ou evidência de testes.
