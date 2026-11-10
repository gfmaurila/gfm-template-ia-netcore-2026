# Container da API

Futuro Dockerfile deverá publicar somente a API, usar runtime suportado, usuário não privilegiado, porta explícita, integridade/prontidão (readiness) apropriados e configuração externa. Não embutir certificados privados, connection strings ou appsettings com segredos.

Validar imagem por varredura, tamanho, SBOM/proveniência se adotados e teste de inicialização em ambiente isolado.
