# Ambientes

Separar configuração de desenvolvimento, teste, homologação e produção. Versionar somente defaults não sensíveis e exemplos fictícios; segredos vêm de mecanismo apropriado por ambiente.

Validar esquema e configuração obrigatória na inicialização; falhar explicitamente em config inválida. Nunca usar fallback para endpoint/credencial de produção.
