# Estratégia de DevOps Front-end

Este documento define práticas futuras; não cria Dockerfiles, manifests, pipelines ou configurações executáveis.

## Web local e Full Stack

- Documentar pré-requisitos e versões após seleção da stack.
- Servir Web pelo tooling/framework escolhido e apontar para API isolada; evitar credenciais reais.
- Docker Compose Full Stack pode orquestrar Web/API e dependências temporárias quando trouxer reprodutibilidade. Banco e mensageria devem ser efêmeros, identificados e descartáveis.
- Testes de integração que usam banco seguem `docs/testing/integration-database-policy.md`; testes puramente visuais/unitários não precisam de banco.
- Diferenciar configuração de desenvolvimento, teste e produção; nunca usar fallback silencioso para endpoint/segredo produtivo.

## GitHub Actions e quality gates

Fluxo de trabalho futuro de PR deve selecionar somente validações pertinentes:

1. Instalar runtimes/dependências a partir de lockfile revisado e cache seguro.
2. Executar format/lint, verificação de tipos, testes unitários e testes de componentes.
3. Executar integração com mocks ou serviços efêmeros; E2E com ambiente isolado e encerramento e limpeza validado.
4. Executar verificações de acessibilidade selecionadas, dependências e segredos.
5. Produzir compilação e validar artefato sem publicar segredos em logs/artefatos.

Publicação exige branch protegida, artefato identificado, revisão e aprovação explícita em ambiente protegido; sem implantação de produção automático por padrão. OIDC e permissões mínimas quando compatíveis.

## React Native e Docker

Docker pode executar análise/testes auxiliares e serviços backend; não substitui Android SDK/iOS toolchain, emuladores, simuladores, signing ou compilações nativos. Planejar executores/serviços compatíveis com o alvo, segredos de assinatura no mecanismo protegido da plataforma e aprovação para distribuição. Nunca incluir keystores/certificados no repositório, imagem ou cache.
